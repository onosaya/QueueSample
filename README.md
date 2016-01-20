# QueueSample
リングバッファによるキューの実現

import java.util.Scanner;
public class QueueSample {
	public static void main(String[] args) {
		Scanner stdIn = new Scanner(System.in);
		Queue s = new Queue(100);
		
		while (true) {
			System.out.println("データ数：" + s.size() + " / "
										+ s.capacity());
			System.out.print("(1)エンキュー　(2)デキュー　(3)ピーク　(4)ダンプ　(0)終了：");
			
			int menu = stdIn.nextInt();
			if (menu == 0) break;
		
			int x;
			switch (menu) {
			 case 1: // エンキュー
				System.out.print("データ：");
				x = stdIn.nextInt();
				try {
					s.enque(x);
				} catch (Queue.OverflowIntQueueException e) {
					System.out.println("キューが満杯です。");
				}
				break;
				
			 case 2: // デキュー
				try {
					x = s.deque();
					System.out.println("デキューしたデータは" + x + "です。");
				} catch (Queue.EmptyIntQueueException e) {
					System.out.println("キューが空です。");
				}
				break;
				
			 case 3: // ピーク
				try {
					x = s.peek();
					System.out.println("ピークしたデータは" + x + "です。");
				} catch (Queue.EmptyIntQueueException e) {
					System.out.println("キューが空です。");
				}
				break;
				
			 case 4: // ダンプ
				s.dump();
				break;
			}
		}
	}
}
