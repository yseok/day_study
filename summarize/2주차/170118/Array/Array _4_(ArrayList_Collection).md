import java.util.ArrayList;

public class Collections {

	public static void main(String[] args) {
		
		String myName = "yusook";
		String Goomingi = "Goo Mingi";
		String leeJunseok = "lee Junseok";
		String seokYang = "seok Yang"; 
		
		
		/*String aaa[] = new String[5];
		aaa[0]=myName; // "yuseok"
		aaa[1] = Goomingi;
		*/
		
		int num = 57;
		
		// ArrayList nameList = new ArrayList(); //라이브러리 목록 import 유틸 패키지가 있다. ArrayList메소드는 import 해줘야 한다.
		
		ArrayList<String> nameList = new ArrayList<>();  // 제네릭 String만 하겠다고 지정함. 앞에 ArrayList<String>으로 설정하면 뒤에는 유추 가능하므로 new ArrayList<>로만 써도 된다.
		
		// class로 선안만 할때는 객체, new로 새로 선언했을때는 인스턴스.
		// 객체는 객체지향으로 코딩을 하기위해 개념화 시켜놓은 대상들. 코드랑 상관이 없는 상태. 국내에서는 인스턴스도 객체로 섞어서 사용하기도 한다.
		// 설계단계의 개념화된, 앞으로 코딩하여야 할 대상.
		// class는 개념화된 대상을 코딩한 대상
		// 코드를  실행해서 메모리에 올라간 순간 인스턴스가 된다. new로 메모리에 올리는 순간 인스턴스화 된다.
		
		// new ArrayList()에서 ArrayList를 Heep에 올라가서 nameList에 할당한다.
		
		nameList.add(myName);
		nameList.add(Goomingi);
		nameList.add(leeJunseok);
		nameList.add(seokYang);

	
		// for each = add한 것에서 하나하나의 name을 꺼내올 수 있다.
			for (Object item : nameList) { // name을 String으로 하면 오류가 뜬다. 
				// String temp = item.toString();
				System.out.println(item); // 이미 앞에서 Object를 String으로 한정했으므로 바로 사용할 수 있다.
				System.out.println(nameList.indexOf(item)); //indexOf는 지정한 것이 어느위치에 있는지 위치번호를 출력한다.
				} 
				
		// System.out.println("2번째 사람 = " + nameList.get(3)); 한줄짜리
		
		/* int i=0;
		for (i=0; i < nameList.size(); i++) { // size는 배열의 크기를 불러운다.
				System.out.println(nameList.get(i));
				nameList.remove(2); // 중간에 제거하게되면 값이 달라지게 된다.
				*/
				// 동적배열의 사이즈는 기준으로 삼으면 안된다.
		
				
		/*int i=0;
		int nameListSize = nameList.size(); // 동적으로 변하므로 for문 바깥에 선언해준다.
		
		for (i=0; i < nameList; i++) { // size는 배열의 크기를 불러운다.
			System.out.println(nameList.get(i));
		}
		*/
			
				
	}
}
