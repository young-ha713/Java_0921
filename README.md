# Java_0921  
  
  
  
  
클래스 : 객체정의.설계도.구성요소 - 전역변수(변수란 값을 저장하는 공간.주기억장치에 할당),  
        메소드 정의(특정기능을 수행하는것).생성자는 메서드다.그리고 클래스 이름과 동일하다.객체가 만들어질때 호출된다.재호출 불가  
객체 :실제 내가 사용
  
***클래스는 객체가 아님.객체를 정의 new 생성자();이런 식으로 연산자가 있어야 객체가 만들어진다***  
***클래스는 레시피 ,레시피로 만든 실제 음식이 객체***
  
  
선언문  
1. 자료형 -기본형이냐 참조형(클래스 형태로 정의 또는 제공받음)이냐
2. 변수명- 변수의 이름
3. 초기값- =뒤에오는  
객체는 new 연산자로 만들고 힙에 저장한다.그리고 참조변수는 객체의 주소값을 저장
  
  
자료형  
1. 원시타입 : 변수 값이 데이터
2.참조타입: 변수의 값이 객체의 주소값  
  
  
메서드  
메서드는 특정 기능을 정의한것. 정의부와 호출부 따로 기억  
호출부는 정의된 메서드의 기능을 사용하는곳. ㅇㅖ를 들어 String ="aaa" ; a.contains(); //메서드 호출  
메서드는 접근제어자 리턴타입 메서드명 (매개변수){}  
  
리턴타입은 메서드가 호출되고 메서드가 실행되고 결과물을 호출부로 리턴한다.  
이때 리턴하는 값이 리턴되고 리턴값의 타입이 리턴타입이 된다.메서드 정의에서 리턴타입을 기입한다.  
  
  
객체 정의는 즉 클래스를 정의하는것을 의미. 클래스는 전역변수와 메서드로 구성  
전역변수는 데이터를 기억하는것 .메서드는 기능을 수행하는것(여기서 메서드는 정의를 의미)
  
  
여기까지는 무조건 암기  
  
배열은 순차적인 자료형,고정길이를 가지고있다. 인덱스는0 부터 시작  
만약 사이즈 선언을 10으로 했는데 20으로 확장의 필요가 있다면 배열은 수정이 불가능하다.  
  
자바에서 제공하는 어레이리스트는 순차적 자료형,인덱스 0부터  
배열과 비슷.다른점은 길이가 가변적  
  
----------------------------------------------------  
  
```
package Test;

import java.util.ArrayList;

public class Test {
	//테스트용 클래스
	public static void main(String[] args) {
		/*
		 * 객체를 여러개 만들었고 이 객체를 하나의 변수로 다루기 위해 배열을 사용했다.
		 * 배열의 특징:연속적 공간, 순서가 있다. 선언된 배열의 크기를 변경하기 힘들다(단점)
		 * 			공부방법 : 길이,인덱스 (0)부터 시작
		 * 자바 개발에서는 ArrayList 자료형을 많이 사용한다
		 * 리스트의 하위 개념이 어래이 리스트 일반적으로 자바에서는 리스트라고 많이 이야기함
		 * List의 특징: 연속공간,순서있음,크기 유동적(사용하는 만큼) 사용하기 더 편하다
		 * 		공부방법: 사이즈,인덱스(0부터 시작)
		 * 실제 면접에서 배열과  list의 특징은 단골 질문입니다.
		 */
		
		Member m = new Member("kkk",11);
		m = new Member("ttt",22); //선언문 아님 초기값 없어서?? 위의 kkk 부분 주소값이 이걸로 바뀌고 위의값은 가비지컬랙터가 없애줌
		
		Member m1 = new Member("kkk",111);//내용이 같을뿐 같은 객체는 아님  
		m1=m;
		
		//선언
		Member[]mlist1 = new Member[10];
		ArrayList<Member> mlist2 = new ArrayList<>();
		
		System.out.println(mlist1.length);
		System.out.println(mlist2.size());
		
		//입력
		Member m1 = new Member("kim",11);
		Member m2 = new Member("lee",22);
//		for(int i = 0; i<mlist1.length;i++) {
//			if(mlist1[i]==null) {
//				mlist1[i]=m1;
//				break;
//			}
//		}
		System.out.println("----------");
		mlist2.add(m1);
		mlist2.add(m2);
		mlist2.add(m2);
		//값 가져오기.배열
//		for(int i=0;i<mlist1.length;i++) {
//			if(mlist1[i]!=null) {
//				mlist1[i].prt();
//			}
//		}
        //값가져오기
		mlist2.get(0); //리턴된 주소 무시
		Member mm = mlist2.get(0);
		Member mm1 = mlist2.get(1);
		System.out.println(mlist2.get(0));
		System.out.println(mlist2.get(1));
		System.out.println(mlist2.get(2));

		//리스트에서 값 가져오기 
//		for(int i=0; i<mlist2.size();i++) {
//			mlist2.get(i).prt();
//		}
	
		//1 이름 
		mlist2.get(1).name="park";
		//2
		for(int i =0; i<mlist2.size();i++) {
			mlist2.get(i).prt();
		}
		//3
		m2 = new Member("choi",33);
		mlist2.add(m2);
		//4
		for(int i =0; i<mlist2.size();i++) {
			mlist2.get(i).prt();
		}
		//5 삭제
		mlist2.remove(0);
		System.out.println("-------------");
		for(int i =0; i<mlist2.size();i++) {
			mlist2.get(i).prt();
		}
		
		//7이름만 출력
		for(int i =0; i<mlist2.size();i++) {
			System.out.println(mlist2.get(i).name);
		}
		
		
		
		
		
		
	}
}
```
  
  
-----------------------------------------
  
  
arrayList  
```
package Test;

import java.util.ArrayList;

public class Test {
	//테스트용 클래스
	public static void main(String[] args) {
		//선언
		ArrayList<Member> mlist = new ArrayList<>();
		
		System.out.println(mlist.size()); //현재 길이
		
		//삽입,추가
		Member m = new Member("a",1);
		mlist.add(m);
		System.out.println(mlist.size());
		
		m = new Member("b",1);
		mlist.add(m);
		System.out.println(mlist.size());
		mlist.add(m);
		System.out.println(m);
		System.out.println(mlist.size());
		
		//삭제
		mlist.remove(1);
		System.out.println(mlist.size());

		//mlist.clear(); //완전 삭제
		System.out.println(mlist.size());

		//가져오기
		mlist.get(0).prt();
		mlist.get(1).prt();
		
		for(int i=0; i<mlist.size();i++) {
			mlist.get(i).prt();
		}//다 돌면서 가져오기
		
		
	}
}
```
  ![arraylist](https://user-images.githubusercontent.com/80766275/191395581-4ebb9665-68e2-494a-835d-7ead3cef4e2c.PNG)
  
  
  


  
  
  
