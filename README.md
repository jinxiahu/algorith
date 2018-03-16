# algorith
剑指offer中的算法实现
两个栈实现队列
package testoffer;


import java.util.Stack;

public class SolutionQueue {
    Stack<Integer> stack1 = new Stack<Integer>();
    Stack<Integer> stack2 = new Stack<Integer>();
    
    public void push(int node) {        
          stack1.push(node);            
    }

    
    public int pop() {  
        if(stack1.empty()&&stack2.empty()){
              throw new RuntimeException("Queue is invalid");
        }
       if(stack2.isEmpty()){
        while(!stack1.empty()){
           stack2.push(stack1.pop());
       }
      }
        return stack2.pop();
      
    }
}
测试代码：
package testoffer;

public class TestSolutionQueue {
	public static void main(String[] args) {
		SolutionQueue queue = new SolutionQueue();
		queue.push(1);
		queue.push(3);
		queue.push(13);
		System.out.println(queue.pop());
		System.out.println(queue.pop());
		System.out.println(queue.pop());		
	}
}
