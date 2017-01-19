# Bbs.java
```
public class Bbs {
	
	private int bbsno;
	private String title;
	private String content;
	private String author;
	private String datetime;
	
	
	public void save(Bbs bbs) {
		데이터베이스.add(bbs)
	}


	public int getBbsno() {
		return bbsno;
	}


	public void setBbsno(int bbsno) {
		this.bbsno = bbsno;
	}


	public String getTitle() {
		return title;
	}


	public void setTitle(String title) {
		this.title = title;
	}


	public String getContent() {
		return content;
	}


	public void setContent(String content) {
		this.content = content;
	}


	public String getAuthor() {
		return author;
	}


	public void setAuthor(String author) {
		this.author = author;
	}


	public String getDatetime() {
		return datetime;
	}


	public void setDatetime(String datetime) {
		this.datetime = datetime;
	}
}
```

#BbsCotroller.java
```
import java.util.ArrayList;
import java.util.Calendar;


  
  @author YS
 
 
public class BbsControler {
	
	private static final String Calender = null;
	ArrayListBbs database;
	int count;
	
	public BbsControler() {
		database = new ArrayListBbs();
		count = 0;
	}
	
	 C(create) R(read) U(Update) D(delete)
	입력함수
	 
	  
	  @param bbs
	 
	public void create(Bbs bbs) {
		count = count + 1;
		bbs.setBbsno(count);
		
		
		bbs.setDatetime(Util.getDatetime());
		database.add(bbs);
	}
	
	bbsno에 해당하는 글 읽기
	  
	  @param bbsno
	  @return
	 
	 특정 글 읽기
	public Bbs read(int bbsno) {
		for (Bbs item  database) { 
			if(item.getBbsno() == bbsno)
				return item;
		}
		return null;
	}
	
	 전체 글 읽기
	  
	  @return
	 
	 전체일기
	public ArrayListBbs readAll() {
		ArrayListBbs list = new ArrayList();
		
		return database;
	}
	
	 수정
	  
	  @param bbs
	 
	public void update(Bbs bbs) {
		 아무것도 안해도 됨
	}
	
	 삭제
	  
	  @param bbsno
	 
	public void delete(int bbsno) {
		for (Bbs item  database) {
			if(item.getBbsno() == bbsno){
				
				database.remove(item);
			}
		}
	}

}

```

#MainBbs.java

```
import java.util.ArrayList;
import java.util.Scanner;

public class MainBbs {

	public static void main(String[] args) {
		
		 컨트롤러 초기화
		BbsControler control = new BbsControler();
		
		Scanner scanner = new Scanner(System.in);
		
		String command =  ;
		boolean runFlag = true;
		
		while(runFlag) {
		
			System.out.println(명령어를 입력하세요.);
			command = scanner.nextLine();
			
			if(command.equals(create)) {
				Bbs bbs = new Bbs();
				System.out.println(제목을 입력하세요.);
				bbs.setTitle(scanner.nextLine());
			
				System.out.println(작성자를 입력하세요.);
				bbs.setAuthor(scanner.nextLine());
				
				System.out.println(내용을 입력하세요.);
				
				String command1 =  ;
				boolean check = true;
				String temp = ;
				
				
				while(check) {
					command1 = scanner.nextLine();

					if (command1.equals(q)){
						check = false;
						System.out.println(내용이 저장되었습니다.);
					} else {
						 temp = temp + System.getProperty(line.separator) + command1;
						temp = temp + command1 + n;
					}
				}
				bbs.setContent(temp);
				
			
				control.create(bbs);
			} else if (command.equals(read)) {
				System.out.println(글번호를 입력하세요  );
				int bbsno = Integer.parseInt(scanner.nextLine());
				control.read(bbsno);
				
			
				Bbs alreadyRead = control.read(bbsno);
				if(alreadyRead != null) {
					System.out.println(글번호   + alreadyRead.getBbsno());
					System.out.println(글쓴이   + alreadyRead.getAuthor());
					System.out.println(제목   + alreadyRead.getTitle());
					System.out.println(내용   + alreadyRead.getContent());
					System.out.println(날짜   + alreadyRead.getDatetime());
				}
			} else if (command.equals(list)){
				ArrayListBbs list = control.readAll();
				for(Bbs item  list) {
					System.out.println(글번호   + item.getBbsno() + , 제목 + item.getTitle());
				}
			}else if (command.equals(exit)) {
				runFlag = false;
				System.out.println(프로그램이 종료되었습니다.);
			}

		}
		
		새글 작성
		int i = 1;
		Bbs bbs = new Bbs();
		
		
		
		bbs.setBbsno(i);
		bbs.setTitle(제목 +i);
		bbs.setContent(내용 +i);
		bbs.setAuthor(작성자 + i);
		
		
		 System.out.println(bbs.getBbsno());
		control.create(bbs);
		
		새글 작성
		i = 2;
		Bbs bbs1 = new Bbs();
				
		bbs.setBbsno(i);
		bbs.setTitle(제목 + i);
		bbs.setContent(내용 + i);
		bbs.setAuthor(작성자 + i);
				
				control.create(bbs1);
				
				
				
				Bbs bbs11 = control.read(i);
				
				System.out.println(bbs11.getTitle());
		}
		
		
	}

}

```

#Utill.java

```

package com.yuseok.Bbs;

import java.util.Calendar;

public class Util {
	public static String getDatetime() {

		Calendar cal = Calendar.getInstance();
		
		int y = cal.get(Calendar.YEAR);
		int M = cal.get(Calendar.MONTH) + 1;   월에 해당하는 기본값이 배열로 [JAN, REB, MAR....]로 되어있다. 그러므로 MONTH에는 +1을 해줘야한다.
		int d = cal.get(Calendar.DATE);
		
		int h = cal.get(Calendar.HOUR);
		int m = cal.get(Calendar.MINUTE);
		int s = cal.get(Calendar.SECOND);
		
		String datetime = y +- + M + - + d +   + h+  + m +  + s;
		
		return datetime;
	}

}

```