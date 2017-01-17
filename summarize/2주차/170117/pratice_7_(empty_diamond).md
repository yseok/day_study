{

	public static void main(String[] args) {
		
		DrawPattern dp = new showTri();
		
		dp.showEntDia(5, "A");

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
	 *  A       A
	 * A         A
	 *  A       A
	 *   A     A
	 *    A   A
	 *     A A
	 *      A
	 * 
	 * @param count
	 * @param unit
	 */
	
	public void showEntDia(int count, String unit) {
		int co, un, k;
		
		for (co = 0; co < count; co++) {
		    for (un = 1; un < count - co; un++) {
		        System.out.print(" ");
		    }
		    
		    for (k = 0 ; k < co * 2 + 1 ; k++) {
		    	
		    	// 문자를 찍는 조건
		    	if( k == 0 || k == co * 2)
		    		System.out.print(unit);
		    	else
		    		System.out.print(" ");
		    }
		    
		    System.out.println();
		}
		
		for (co = count - 1; co > 0; co--) {
		    for (un = count - co; un > 0; un--) {
		        System.out.print(" ");
		    }
		    for (k = co * 2 - 1; k > 0; k--) {
		    	if( k == 1 || k == co * 2 -1)
		    		System.out.print(unit);
		    	else
		    		System.out.print(" ");
		    }
		    System.out.println();
		}
	}
	