{

	public static void main(String[] args) {
		
		DrawPattern dp = new showTri();
		
		dp.showTriEntTwo(5, "A");

	}

	/**
	 *
	 * 아래 예시와 같이 출력하시오.
	 * 
	 * 예) count = 5, unit = A
	 *      A
	 *     A A
	 *    A   A
	 *   A     A
	 *  AAAAAAAAA
	 * 
	 * @param count
	 * @param unit
	 */
	
	public void showTriEntTwo(int count, String unit) {
	int co, un, k;
		

	for(co=0; co<count-1; co++){
		for(un=co; un<count-1; un++){
			System.out.print(" ");
		}
		for(un=0; un<2*co+1; un++) {
			if(un==0 | un==2*co)
				System.out.print(unit);
			else
				System.out.print(" ");
		}
		System.out.println("");
	  	}
	  	for(k=0; k<count*2-1; k++){
	  		System.out.print(unit);
	  	}
	 }
	