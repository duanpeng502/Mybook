##java02作业

1.为考试成绩划定五个级别，当成绩大于或等于90分时，划定为优；

当成绩大于或等于80且小于90时，划定为良；

当成绩大于或等于70且小于80时，划定为中；

当成绩大于或等于60且小于70时，划定为及格；

当成绩小于60时，划定为差.使用if语句

	public class Test1 {

		public static void main(String[] args) {
			System.out.println("请输入你的成绩：");
			Scanner scanner = new Scanner(System.in);//输入操作
			int grade = scanner.nextInt();
			if(grade>=90){
				System.out.println("你的成绩等级为：优");
			}else if(grade<90 || grade>=80){
				System.out.println("你的成绩等级为：良");
			}else if(grade<80 || grade>=70){
				System.out.println("你的成绩等级为：中");
			}else if(grade<70 || grade>=60){
				System.out.println("你的成绩等级为：及格");
			}else if(grade<60){
				System.out.println("你的成绩等级为：不及格");
			}else if(grade<0 || grade>100){
				System.out.println("输入错误，请重新输入");
		}
			scanner.close();
		}
	}

2.使用switch结构重写上面代码

	public class Test2 {

		public static void main(String[] args) {
				String input = JOptionPane.showInputDialog(null,"请输入你的分数");
				int score =Integer.parseInt(input)/10;
				switch(score){
				case 10:
				case 9:
					JOptionPane.showInputDialog(null,"你的成绩等级为:优");
					break;
				case 8:
					JOptionPane.showInputDialog(null,"你的成绩等级为:良");
					break;
				case 7:
					JOptionPane.showInputDialog(null,"你的成绩等级为:中");
					break;
				case 6:
					JOptionPane.showInputDialog(null,"你的成绩等级为:及格");
					break;
					default:
					JOptionPane.showInputDialog(null,"你的成绩等级为:不及格");
					break;
				}
				System.exit(0);
		}
	}

3.给出年份、月份，计算输出该月的天数 使用switch