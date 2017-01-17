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
	 * A
	 * AA
	 * AAA
	 * AAAA
	 * AAAAA
	 * AAAAAA
	 * 
	 * @param count
	 * @param unit
	 */
	public void showRecTri(int count, String unit) {
		int i, j;
		
		for(i = 1; i <= count; i++) {
			for(j = 1; j <= i; j++) {
				// i = 1, j = 1 부터 1까지 동작
				// i = 2, j = 1 부터 2까지 동작
				// i = 3, j = 1 부터 3까지 동작
				System.out.print(unit);
			}
			System.out.println("");
			
		}
	}