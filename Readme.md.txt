package java8;

import java.util.ArrayList;
import java.util.List;
import java.util.Collections;
import java.util.Comparator;

public class Hello {
	
	public static void main(String[] args){
		
		System.out.println("this is mohana");
		
		List<String> ls= new ArrayList<String>();
		
		ls.add("mohana");
		ls.add("joy");
		ls.add("dickson");
		ls.add("kiran");
		ls.add("shlipa");
		
		List<String> ls2= new ArrayList<String>();
		ls2.add("type");
		ls2.add("raj");
		ls2.add("uuy");
		ls2.add("bah");
		ls2.add("hen");
		
		
		
		Hello ref= new Hello();
		
		ref.sortUsingJava7(ls);
		System.out.println(ls);
		
		
		ref.sortUsingJava8(ls2);
		System.out.println(ls2);
		
	}
	
	public void sortUsingJava7(List<String>names){
		 Collections.sort(names, new Comparator<String>() {
	         @Override
	         public int compare(String s1, String s2) {
	            return s1.compareTo(s2);
	         }
	      });
	}
	
	
	public void sortUsingJava8(List<String> names) {
	      Collections.sort(names, (s1, s2) -> s1.compareTo(s2));
	   }

}

package java8;

public class LambdaExcpressionBasicOperation {
	
	public static void main(String[] args){
		
		LambdaExcpressionBasicOperation lambdaExp= new LambdaExcpressionBasicOperation();
		
		MathOperation addition = (int a, int b) -> a + b;
		
		MathOperation subtraction =(a, b)->a-b;
		
		MathOperation multiplication=(int a, int b) -> { return a * b; };
		
		MathOperation division=(int a, int b)-> a/b;
		
		System.out.println(lambdaExp.operate(10, 5, addition) );
		
		System.out.println(lambdaExp.operate(17, 8, subtraction));
		
		
		System.out.println(lambdaExp.operate(10, 2, multiplication));
		
		System.out.println(lambdaExp.operate(25, 5, division));
		
		GreetingService gretingSerive=message->
		System.out.println("Welcome " + message);
		gretingSerive.showMessages("Mohana");
		
		GreetingService gretingService2=message->
		System.out.println("Welcome " + message);
		gretingService2.showMessages("Siva");	
		
	}
	
	interface MathOperation{
		
		int operation(int a, int b);
		
	}
	
	interface GreetingService{
		void  showMessages(String Message);
	}
	
	public int operate(int a, int b, MathOperation mathOperation){
		return mathOperation.operation(a, b);
	}

}

