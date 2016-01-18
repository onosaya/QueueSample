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
			System.out.print("(1)エンキュー　(2)デキュー　(3)ピーク　(
