

http://ra2kstar.tistory.com/144


<pcap 정보 사이트>
https://www.devdungeon.com/content/using-libpcap-c




```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

const int MAX_SIZE = 1000;

int main() {

	FILE *fp = fopen("test.txt", "r");

	char* inp = (char*)malloc(sizeof(char)*MAX_SIZE);

	int i;

	bool HANGUL = false;



	while (fgets(inp, MAX_SIZE, fp)) {

		printf("%s", inp);


		for (i = 0; i < strlen(inp); i++) {

			if ((inp[i] & 0x80) == 0x80) HANGUL = true; //한글인지 확인

			if (!HANGUL)printf("%c  ", inp[i]); //아니면 그냥 출력

			else {

				printf("%c%c", inp[i], inp[i + 1]); //한글이면 2byte 출력

				i++;

			}

			HANGUL = false;

		}

		printf("\n");

	}
}

```
