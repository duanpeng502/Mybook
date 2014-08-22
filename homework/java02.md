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

    public class Test3 {

        public static void main(String[] args) {
            //int day;
            System.out.println("请输入年份：");
            Scanner scanner = new Scanner(System.in);//输入操作
            int year = scanner.nextInt();	
            System.out.println("请输入月份：");
            int month = scanner.nextInt();

            switch(month){
            case 1:
            case 3:
            case 5:
            case 7:
            case 8:
            case 10:
            case 12:
                System.out.println("该月有31天");
                break;
            case 4:
            case 6:
            case 9:
            case 11:
                System.out.println("该月有30天");
                break;
            case 2:
                if(year%4==0){
                    System.out.println("该月有29天");
                }else{
                    System.out.println("该月有28天");
                }
                break;
                default:
                System.out.println("输入错误");
            }
            scanner.close();
        }
    }

    4.计算sum=1+2+3+4+5+…+100 使用for循环

        public class Test4 {

            public static void main(String[] args) {
                int sum=0,i;
                for(i=0;i<=100;i++){
                    sum=sum+i;
                }
                System.out.println("1到100的和为:"+sum);
            }
        }
5.这是一个古典数学问题：一对兔子从它出生后第3个月起，每个月

都生一对小兔子，小兔子3个月后又生一对小兔子，假设兔子都不死

，求每个月的兔子对数。该数列为：1  1  2  3  5  8  13 21…

即从第3项开始，其该项是前两项之和。求100以内的波那契数列 分

别使用for与while循环

    public class Test5 {

        public static void main(String[] args) {
            calculate(1,1);				//传参
        }
        public static void calculate(int first,int second){
            int result=first+second;
            System.out.println("1:"+first);
            System.out.println("2:"+second);
            System.out.print("3:"+result);
            for(int i=0;i<100;i++){
                first=second;						// Fabaccic 算法
                second=result;
                result=first+second;
                System.out.print(i+4+":"+result);
            }
        }
    }


6.计算n!, 当n=9时。并分别输出1！~9！各阶乘的值 使用while循环

	public class Test6 {

		public static void main(String[] args) {
			int n=1;
			while(n<10){
				int answer = n*n;
				System.out.println(n + "阶层为:"+answer);
				n++;
			}
		}
	}

7.输出50~100以内的所有素数。所谓素数即是只能被1和其自身除尽的正整数。

    public class Test7 {

        public static void main(String[] args) {
            int i,j,n=0;
            for(i=50;i<=100;i++){
                for(j=2;j<=i/2;j++)
                    if(i%j==0)
                        break;
                if(j>=i/2+1){
                    if(n%6==1);
                        System.out.println("素数为:"+i);
                        n++;
                }
            }
        } 
    }


8.输出10~1000之间既能被3整除也能被7整除的数

    public class Test8 {

        public static void main(String[] args) {
            int i=0;
            for(i=10;i<=1000;i++)
                if(i%21==0)
                System.out.println("既能被3又能被7整除的数："+i);
                i++;
            }
    }

9.判断一个正整数是否是素数，若是计算其阶乘。判断素数和阶乘作为方法定义，并在主方法中调用它们
    public class Test9 {

        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);//输入操作
            System.out.println("请输入一个数：");
            int n=scanner.nextInt();
            if (isPrime(n)){									//调用isPrime
                System.out.println("该数不为素数");				
            }else{			
                int answer= n*n;			
                System.out.println("该数为素数");
                System.out.println(n+"的阶层为:"+answer);
            }
            scanner.close();
        }
        public static boolean isPrime(int n){
            for(int i=2;i<=n/2;i++){
                if(n%i==0)
                    return true;					//判断是否为素数
            }
            return false;
        }
    }
