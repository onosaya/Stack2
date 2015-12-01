# Stack2
スタック２

import java.util.Scanner;
public class StackSample {
	public static void main(String[] args) {
		Scanner stdIn = new Scanner(System.in);
		Stack s = new Stack(100);
		
		while (true) {
			System.out.println("データ数：" + s.size() + " / "
										+ s.capacity());
			System.out.print("(1)プッシュ　(2)ポップ　(3)ピーク　(4)ダンプ　(0)終了：");
			int menu = stdIn.nextInt();
			if (menu == 0) break;
			
			int x;
			switch (menu) {
			　case 1:
				System.out.print("データ：");
				x = stdIn.nextInt();
				try {
					s.push(x);
				} catch (Stack.OverflowIntStackException e) {
					System.out.println("満杯です．");
				}
				break;
				
			　case 2:
				try {
					x = s.pop();
					System.out.println("データは" + x + "です．");
				} catch (Stack.EmptyIntStackException e) {
					System.out.println("空です．");
				}
				break;
			　case 3:
				try {
					x = s.peek();
					System.out.println("データは" + x + "です．");
				} catch (Stack.EmptyIntStackException e) {
					System.out.println("空です．");
				}
				break;
			　case 4:
				s.dump();
				break;
			}
		}
	}
}
