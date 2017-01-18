 숫자갯수 구하기 (구글면접)

1부터 10,000까지 8이라는 숫자가 총 몇번 나오는가?
 8이 포함되어 있는 숫자의 갯수를 카운팅하는 것이 아니라 8이라는 숫자를 모두 카운팅 해야 한다.
( 예를들어 8808은 3, 8888은 4로 카운팅해야함)

문제 1) 입력값을 정수 n,m으로 받았을때,n이하까지 m의 갯수가 몇개인지 구하시오

입력값n = 10,000 m = 8


***


import java.util.ArrayList;

public class strings {

	public static void main(String[] args) {


int count = 0;

	// 1부터 10000까지 루프
	for(int i=1; i<10000; i++){			

		// i를 String 형태로 변환

		String str = String.valueOf(i);			

		// String형태에서 8문자가 있는지 확인

		if (str.contains("8")){				

			// 8이 있다면 현재 변환된 String의 길이값으로 루프

			for (int j=0; j<str.length(); j++){					

				//  문자형태로 변환해서 8인지 확인

				if ('8' == str.charAt(j)) {

					count++;
					
					}
				}
			}
		}		

	System.out.println(count + "개");
		
	}
}
		