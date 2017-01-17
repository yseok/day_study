	{

	public static void main(String[] args) {
		
		DrawPattern dp = new showTri();
		
		dp.showTri(5, "A");

	}

	/**
	 * 
	 * 아래 예시와 같이 출력하시오.
	 * 
	 * 예) count = 5, unit = A
	 *      A
	 *     AAA
	 *    AAAAA
	 *   AAAAAAA
	 *  AAAAAAAAA
	 * AAAAAAAAAAA
	 * 
	 * @param count
	 * @param unit
	 */
	
	/* for문을 추가하여 형태 만들기.

	public void showTri(int count, String unit) {
		int co, un, k;
		
		for(co = 1; co <= count; co++) {
			// 공백을 출력하는 반복문
			for(k = count - 1; k >= co; k--){
				System.out.print(" ");
			}
			
			// unit을 출력하는 반복문
			for(un = 1; un <= co; un++) {
				System.out.print(unit);
			}
			
			// 맞닿은 칸을 출력
			for(un = 2; un <= co; un++) {
				System.out.print(unit);
			}
			System.out.println("");
		}
	}
	*/


	public void showTriTwo(int count, String unit) {
		int co, un, k;
		
		for (co = 0; co < count; co++) {
		    for (un = 1; un < count - co; un++) {
		        System.out.print(" ");
		    }
		    // 공백을 찍는 조건
		    for (k = 0; k < co * 2 + 1; k++) {
		        System.out.print(unit);
		    }
		    System.out.println();
		}
	}