
		String a = "158766";
		String b = "12345";
		String c = "158766";
		
		// 1. 문자열 비교
		// 문자열.compareTo(문자열)
		// 문자열.equals(문자열)
		// 문자열 == 문자열
		
		System.out.println(a.compareTo(b));
		System.out.println(a.compareTo(c));
		
		
		// equals를 많이쓴다.
		System.out.println(a.equals(b));
		System.out.println(a.equals(c));
		
		if(a.equals(b)){ // 숫자 제외한 문자를 비교하기 위해서는 equals를 사용
			System.out.print("a와 b가 같습니다.");

		// 2. 문자열의 인덱스 값
		System.out.println(a.charAt(2));
		//  위치를 가리키니다
		// a  b  c  d  e  f  g
		//1  2  3  4  5  6  7 
		
		// 3. 문자열 합치기
		System.out.println(a+b);
		
		// 4. "무엇"으로 시작하는 문자열인지 파악
		System.out.println(a.startsWith(c, 23));
		System.out.println(a.endsWith("31"));
		
		// 5. 찾고자 하는 문자열이 몇번재 있는지
		// 찾는 문자열이 없으면 -1
		System.out.println(a.indexOf("3"));
		
		// 6. 문자열 길이
		System.out.print(a.length());
		
		// 7. 문자열 변경
		System.out.println(a.replace("1","x"));
		a.replaceAll("문자열의 패턴 : 정규식", "바꿀문자");
		
		// 8.문자열 자르기
		System.out.println(a.substring(4));
		System.out.println(a.substring((int) 3, 4)); //3과 4 인덱스 사이의 인덱스 문자를 가져온다.
		
		
		// 9.문장열 분리하기
		String value = "a/b/cdg/a2223/afefa";
			String values[] = value.split("/");
			for (String item : values) {
				System.out.println(item);
			}
		}
		
		
		// 10. 숫자 -> 문자변환 = 숫자 + ""
		int abc = 12345;
		// 숫자 -> 문자변환 = 숫자 + ""
		String ccc = 888 + ""; // "888"
		
		// 11. 문자 -> 숫자변환
		int ddd = Integer.parseInt(ccc);
		long eee = Long.parseLong(ccc);
		
		// 12. int -> char 변환 = char 범위보다 큰 값이 입력되면 절삭됨
		char fff = (char) ddd;
		
		// 13. 하나의 숫자를 char로 변형 = 이유 : 문자열보다 효율적. 문자열을 여러개의 문자를 저장하기 위한것
		int argNum = 8; //입력하는 숫자
		int argDigix = 10; //진법
		char cha = character.forDigit(argNum, argDigix);
		
		// 14. 문자열을 한글자씩 char로 분해
		String target = "af8f8ad8e8rts";
		char arrs[] = target.toCharArray();
		
		// 15. 배열 정렬
		Array.sort(arrs);
		// arrs = 정렬되었습니다.
