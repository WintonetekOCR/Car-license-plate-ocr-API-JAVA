# Sinosecu Car plate license OCR API interface calling source code 
 

 ## Introduction
 License plate recognition service can quickly and accurately identify ordinary blue license plates, ordinary yellow license plates (single layer), double-layer yellow license plates, new energy license plates, military license plates, armed police license plates, embassy license plates, agricultural license plates and other specifications of car license plates

 ### JAVA SOURCE CODE
 ```package com.test;

import okhttp3.*;
import org.json.JSONObject;
import java.io.*;
/**
 * 需要添加依赖
 * 
 * 
 *     com.squareup.okhttp3
 *     okhttp
 *     4.12.0
 * 
 */
class Sample {

	static final OkHttpClient HTTP_CLIENT = new OkHttpClient().newBuilder().build();

	public static void main(String []args) throws IOException{
		MediaType mediaType = MediaType.parse("text/plain");
		RequestBody body = new MultipartBody.Builder().setType(MultipartBody.FORM)
		  .addFormDataPart("img","/9j")
		  .addFormDataPart("key","M***********g")
		  .addFormDataPart("secret","3***********6")
		  .addFormDataPart("typeId","19")
		  .addFormDataPart("format","json")
		  .build();
		Request request = new Request.Builder()
		  .url("https://netocr.com/api/recogliu.do")
		  .method("POST", body)
		  .build();
		Response response = HTTP_CLIENT.newCall(request).execute();
		System.out.println(response.body().string());
	}
}```



