public class Array {

	public static void main(String[] args) {

		// 3차원 배열
		x = 5;
		y = 10;
		z = 7;
		
		int array3[][][] = new int[z][y][x];
		
		array3[3][5][2] = 352;
		array3[2][0][3] = 203;
		array3[6][9][1] = 691;
		
		int zIndex = 0;
		int yIndex = 0;
		int xIndex = 0;
		
		for(zIndex=0; zIndex < z; zIndex++) {
			for(yIndex=0; yIndex < y; yIndex++) {
				for(xIndex=0; xIndex < x; xIndex++) {
					System.out.print("[" + array3[zIndex][yIndex][xIndex] + "]");
				}
				System.out.println("");
			}
			System.out.println("----------------------------");
		}
	}

}
