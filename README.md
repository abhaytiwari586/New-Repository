# New-Repository
Yupp
https://curl.haxx.se/libcurl/c/http-post.html
posting data to thingspeak using R-Pi and C language
*************************************************************************************************************************
*************************************************************************************************************************
#include <stdio.h>
#include <curl/curl.h>

int main(void)
{
  int data1 = 5;
  int data2 = 3;
  while(1){
  CURL *curl;
  CURLcode res;

  curl_global_init(CURL_GLOBAL_ALL);

  curl = curl_easy_init();
 // curl = curl_easy_init();

  if(curl){

    curl_easy_setopt(curl, CURLOPT_URL, "http://api.thingspeak.com/update?api_key=OYWB5897YCUE9BOS");

    curl_easy_setopt(curl, CURLOPT_POSTFIELDS, "field1=1.5");
    curl_easy_setopt(curl, CURLOPT_POSTFIELDS, "field2=4.6");
    res = curl_easy_perform(curl);

    if(res != CURLE_OK)
      fprintf(stderr, "curl_easy_perform() failed: %s\n", curl_easy_strerror(res));

      curl_easy_cleanup(curl);
   }}
    curl_global_cleanup();
    return 0;
  }
