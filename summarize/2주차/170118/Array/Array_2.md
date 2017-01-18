public class Array {

	public static void main(String[] args) {

		// 2차원 배열 선언
		// {434, 98384, 0, 0, 0, 8377}
		// {434, 98384, 0, 0, 0, 8377}
		// {434, 98384, 0, 0, 0, 8377}
		// {434, 98384, 0, 0, 0, 8377}
		// {434, 98384, 0, 0, 0, 8377}
		
		int array2[][] = new int[3][2]; // [y][x]의 순서
		//         y x
		
		array2[0][0] = 1;
		array2[0][1] = 2;
		array2[1][0] = 3;
		array2[1][1] = 4;
		array2[2][0] = 5;
		array2[2][1] = 6;

		int x,y,z;
		
		/*for(y = 0; y < 3; y++) {
			for(x=0; x < 2; x++) {
				System.out.print("[" +array2[y][x] + "]");
			}
			System.out.println("");
		}*/
		
		// 데이터 셋의 크기, [번호, 제목, 내용, 날짜]
		// x축을 먼저 정의하고
		// x축 괄호 앞에 y축의 공간을 정의해 준다.
		int array2_1[][] = new int[100][4];
		
		/* for(y = 0; y < 100; y++) {
			System.out.print((y+1) + "번째 줄 ");
			
			for(x=0; x < 4; x++) {
				System.out.print("[" +array2_1[y][x] + "]");
			}
			System.out.println("");
		} */
		