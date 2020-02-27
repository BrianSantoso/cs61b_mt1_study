# cs61b_mt1_study

# API Links:


Iterable: https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html
Collection: https://docs.oracle.com/javase/8/docs/api/java/util/List.html
List: https://docs.oracle.com/javase/8/docs/api/java/util/List.html
Iterator: https://docs.oracle.com/javase/8/docs/api/java/util/Iterator.html
LinkedList: https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html

![enter image description here](https://3.bp.blogspot.com/-C1o1u8il4J8/XGGvQJlvA1I/AAAAAAAACs8/MCU7ydkwW0oF63BNiVA62OkWtHwIGk0SACLcBGAs/s1600/Screenshot+%2528286%2529.png)

``` // Function to swap next and prev pointers of the given node
	public static void swap(Node node)
	{
		Node prev = node.prev;
		node.prev = node.next;
		node.next = prev;
	}

	// Recursive function to reverse a doubly linked list
	public static Node reverse(Node head, Node curr)
	{
		// last node
		if (curr.next == null)
		{
			// swap next and prev pointers for the current node
			swap(curr);

			// update head
			head = curr;
			return head;
		}

		// swap next and prev pointers for the current node
		swap(curr);

		// recur with the next node
		head = reverse(head, curr.prev);
		return head;
	}

	// Function to reverse a doubly linked list
	public static Node reverseDDL(Node head)
	{
		// stores the previous node and the current node
		Node curr = head;

		// pass current node and previous node information in the recursion itself
		head = reverse(head, curr);
		return head;
	} ```
