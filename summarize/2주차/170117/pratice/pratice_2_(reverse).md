	{

	public static void main(String[] args) {
		
		DrawPattern dp = new DrawPattern();
		
		dp.showRecTri(5, "A");

	}

	/**
	 * 
	 * 아래 예시와 같이 출력하시오.
	 * 
	 * 예) count = 5, unit = A
	 *      A
	 *     AA
	 *    AAA
	 *   AAAA
	 *  AAAAA
	 * AAAAAA
	 * 
	 * @param count
	 * @param unit
	 */
	
	public void showReverseTri(int count, String unit) {
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
			// 줄바꾸기
			System.out.println("");
		}
	}
	
	/*변형
	public void showReverseTri2(int count, String unit) {
		int i, j, k;
		
		for(i = 1; i <= count; i++) {
			// 공백을 출력하는 반복문
			for(k = count - 1; k >= i; k--){
				System.out.print(" ");
			}
			
			// unit을 출력하는 반복문
			for(j = 1; j <= i; j++) {
				if(j <= count -i)
				    System.out.print("");
				else
					System.out.print(unit);
			}
			System.out.println("");
		}
	}