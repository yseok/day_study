public class Array {

	public static void main(String[] args) {
		
		// 1차원 배열 선언
		
		// {434, 98384, 0, 0, 0, 8377}
		// x0     1     2  3  4   5
		
		int array[] = new int[6];
		// int[] array = new int[6]; 취향따라.
		
		/*ex)
		 * int array[] = new int[6];
		 * intsea;
		 * int[] dsflajkf;
		 * int aaa;
		 * int bbb;
		 * int[] aflkalef;
		 * 
		 * 코드캡쳐에 유리하다.
		 * 결과는 이상없으므로 취향따라 쓰면 된다.
		 */
	
		
		// 배열 입력
		array[0] = 434;
		array[1] = 98384;
		array[5] = 8377;
		
		// 	범위를 넘어섰기 때문에 오류
		// array[6] = 56464;
		
		System.out.println(array[1]);
		System.out.println(array[2]); // [2]는 숫자를 입력하지 않았지만 메모리설정할때 0으로 초기화 된다.
		// 배열에서만 자동으로 0으로 초기화.
		