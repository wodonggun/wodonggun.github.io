---
layout: post
title: "우분투에서 IPsec 스니핑 설정 - IPsec Sniffing setting"
subtitle: <span class="evidence">실제 Linux단에서 패킷 송수신 과정을 스니핑하기</span>
date: 2018-09-05
author: NoonGam
category: Study
tags: Network Linux
comments: true  
finished: true
---



## IPsec - Internet Protocol Security

> IPSec은 Internet Protocol Security의 약어로서 통신중 network layer에서의 보안을 위한 표준이다. IPSec은 인터넷 상에서 VPN(Virtual Private Network)을 구현하는데 사용될 수 있도록 IETF (Internet Engineering Task Force)에서 개발된 protocol set이다. 이는 네트워크상의 IP layer에서의 보안에 중점을 두었으며, 사설 및 공중망을 사용하는 TCP/IP 통신을 보다 안전하게 유지하기 위한 end-to-end encryption과 authentication을 제공한다.

1. 네트워크계층(IP 계층) 상에서 IP 패킷 단위로 `인증`,`암호화`,`키관리`를 하는 프로토콜

2. VPN을 구현하기 위해 만든 프로토콜(Tunnel Mode)

3. Transport계층 아래에서 구현되며, 운영체제에서 IPsec을 지원함.


$ sudo apt-get update

$ sudo apt-get install libpcap-dev

$ ln -s /usr/include/pcap/bpf.h /usr/include/net/bpf.h


$ gcc snif.c -o snif -lpcap
$ ./snif enp0s8 (super user)



## Ascii Ascii-extend  UTF-8

UTF-8 최소 8비트로 이루어진 데이터타입
한글은 UTF-8의 8비트 3개가 보여 24비트가 하나의 한글을
표현할 수 있다.


## data sniffing
snif.c

```c
#include <pcap.h>
#include <stdio.h>
#include <stdlib.h> // for exit()
#include <net/ethernet.h>
#include <netinet/tcp.h>   //Provides declarations for tcp header
#include <netinet/ip.h>    //Provides declarations for ip header

void print_data (const u_char * data , int Size)
{
    int i , j;

    for(i=0 ; i < Size ; i++) {
        if( i!=0 && i%16==0) {  //if one line of hex printing is complete...
            printf("         ");
            for(j=i-16 ; j<i ; j++) {
                if(data[j]>=32 && data[j]<=128)
                  printf("%c", (unsigned char)data[j]);
		else if(data[j]>=234 && data[j] <=237){

		printf("%c%c%c",(unsigned char)data[j],(unsigned char)data[j+1],(unsigned char)data[j+2]);
	j+=2;	}
		else if(data[j]==10)
			printf(" \b");
		else if(data[j]<=32)
			printf(" \b");
                else
                  printf(" \b");
            }
            printf("\n");
        }

        if(i%16==0)
          printf("   ");
            printf(" %02X",(unsigned int)data[i]);

        if( i==Size-1) {  //print the last spaces
            for(j=0;j<15-i%16;j++)
              printf("   "); //extra spaces
            printf("         ");
            for(j=i-i%16 ; j<=i ; j++) {
                if(data[j]>=32 && data[j]<=128)
                  printf("%c",(unsigned char)data[j]);
		else if(data[j]>=234 && data[j] <=237){
                printf("%c%c%c",(unsigned char)data[j],(unsigned char)data[j+1],(unsigned char)data[j+2]);
        j+=2;   }
		else if(data[j]==10)
			printf(" \b");
                else if(data[j]<32)
                  printf(" \b");
		else
			printf(" \b");
            }
            printf("\n" );
        }
    }
}

void print_esp_packet(const u_char * Buffer, int Size)
{
    if (Size > 363) {
      print_data(Buffer + 363, Size - 363 );
    }
}

void print_tcp_packet(const u_char * Buffer, int Size)
{
    unsigned short iphdrlen;

    struct iphdr *iph = (struct iphdr *)( Buffer  + sizeof(struct ethhdr) );
    iphdrlen = iph->ihl*4;

    struct tcphdr *tcph=(struct tcphdr*)(Buffer + iphdrlen + sizeof(struct ethhdr));

    int header_size =  sizeof(struct ethhdr) + iphdrlen + tcph->doff*4;

    if (Size > 322) {
      print_data(Buffer + 322, Size - 322 );
    }
}

void process_packet(u_char *args, const struct pcap_pkthdr *header, const u_char *buffer)
{
    int size = header->len;

    //Get the IP Header part of this packet , excluding the ethernet header
    struct iphdr *iph = (struct iphdr*)(buffer + sizeof(struct ethhdr));
    switch (iph->protocol) //Check the Protocol and do accordingly...
    {
        case 6:  //TCP Protocol
            print_tcp_packet(buffer , size);
            break;
        case 50:  //ESP Protocol
            print_esp_packet(buffer , size);
            break;
    }
}

int main(int argc, char* argv[])
{

   char errbuf[100] , *devname;
   pcap_t *handle; //Handle of the device that shall be sniffed

   printf("argc : %d\n\n\n\n\n",argc);//command count print
   printf("str0: %s\n",argv[0]);
   printf("str1: %s\n",argv[1]);
   if (argc == 1) {
     fputs("\nUsage ./snif devname(ex. eth0)\n\n", stderr);
     exit(1);
   }

    devname = argv[1];

    //Open the device for sniffing
    printf("Opening device %s for sniffing ... " , devname);
    handle = pcap_open_live(devname , 65536 , 1 , 0 , errbuf);

    if (handle == NULL)
    {
        printf("Couldn't open device %s\n" , devname);
        exit(1);
    }
    printf("Done\n");

    //Put the device in sniff loop
    pcap_loop(handle , -1 , process_packet , NULL);
    printf("loop end");
    return 0;
}

```



<br><br><br>


## 정리

<a>아직 정리해야 할 일들이 많아서 조금씩 업데이트 하겠습니다.</a>
