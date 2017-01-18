# anagram

- 문자열의 구성이 같은 문자열을 아나그램이라고 한다

> 예) abcd = acbd = cadc

문제1) 입력값을 문자열 n,m으로 받은 후, n문자열과 m문자열이 아나그램인지 확인하는 프로그램을 작성하세요

조건.
아나그램일 경우 결과값으로 true를 리턴한다.


***


package com.yuseok;

import java.util.ArrayList;

public class strings {

	public static void main(String[] args) {

	
	strings s = new strings();
		String result = s.reverseString("anything");
		System.out.println(result);
	}
	
	public String reverseString(String input) {
		char result[] = new char[input.length()];
		char array[] = input.toCharArray();

		int arraylength = array.length;
		int count = 0;
		int index = 0;
		
		String reverse = "";
		
		for(index=arraylength -1; index >=0; index--){
			result[count] = array[index];
			count++;
		}
		
		for(index = 0; index<arraylength; index++){
			reverse = reverse + Character.toString(result[index]);
		}
		
		
		return reverse;

	}
	
}