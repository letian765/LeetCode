```java
public class Stack {
	private ListNode head;

	public Stack() {
		head = null;
	}

	public Integer pop() {
		if (head == null) {
			return null;
		}
		ListNode cur = head;
		head = head.next;
		cur.next = null;
		return cur.val;
	}

	public void push(int val) {
		ListNode newHead = new ListNode(val);
		newHead.next = head;
		head = newHead;
	}

	public Integer peek() {
		if (head == null) {
			return null;
		}
		return head.val;
	}
}

public class Queue {
	ListNode head;
	ListNode tail;
	public Queue() {
		head = null;
		tail = null;
	}

	public void offer(int val) {
		if (head == null) {
			head = new ListNode(val);
			tail = head;
		} else {
			tail.next = new ListNode(val);
			tail = tail.next;
		}
	}

	public Integer poll() {
		if (head == null) {
			return null;
		}
		ListNode cur = head;
		head = head.next;
		if (head == null) {
			tail = null;
		}
		cur.next = null;
		return cur.val;
	}

	public Integer peek() {
		if (head == null) {
			return null;
		}
		return head.val;
	}
}

public class BoundedStack {
	int[] array;
	int head;

	public BoundedStack(int cap) {
		array = new int[cap];
		head = -1;
	}

	public void push(int val) {
		array[++head] = val;
	}

	public Integer pop() {
		return head == -1 ? nulll : array[head--];
	}

	public Integer peek() {
		return head == -1 ? nulll : array[head];
	}
}

public class Queue {
	int[] array;
	int head;
	int tail;

	public Queue(int cap) {
		array = new int[cap];
		head = 0;
		tail = -1;
	}

	public boolean offer(int val) {
		if (head == tail) {
			return false;
		}
		array[tail] = val;
		tail = (tail + 1) % array.length;
	} 

	public Integer poll() {
		if (head + 1 == tail) {
			return null;
		}
		head = (head + 1) % array.length;
		return array[head];
	}

	public Integer peek() {
		return head + 1 == tail ? null : array[(tail+1) % array.length];
	}
}
```
