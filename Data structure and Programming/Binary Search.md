```

using System;
					
public class Program
{
	public static void Main()
	{
		int[] arr = {1,2,3,4,5,6,7,8,9};
		Console.WriteLine(BinarySearch(arr, arr.Length, 10));
	}
	
	public static int BinarySearch(int[] arr, int length,  int target){
		int start = 0;
		int end  = (length -1);
		
		while(start <= end){
			int mid = (start + end)/2;
			Console.WriteLine(mid);
			if(arr[mid] == target)
				return arr[mid];
			else if(arr[mid] < target)
				start = mid + 1;
			else 
				end = mid -1;
		    }
			return -1;
	}
}

```



steps: 

1. iterate over array from 0 to n-1;
2. if


using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace BST
{
    class Program
    {
        static void Main(string[] args)
        {
            int[] arr = { 7, 3, 1, 5, 6, 4, 8, 9 };
            Node root = null;
            for (int i = 0; i < arr.Length; i++)
            {
                root = InsertNode(root, arr[i]);
            }
            int[] arr1 = { 7, 3, 1, 4, 6, 4, 8, 9 };
            Node root1 = null;
            for (int i = 0; i < arr1.Length; i++)
            {
                root1 = InsertNode(root1, arr1[i]);
            }
            Console.WriteLine("Inorder traversal of BST in Recusrsive");
            TraversInorderRecursive(root);
            Console.WriteLine();

            Console.WriteLine("Inorder traversal of BST in Iterative");
            TraversInorderIterative(root);
            Console.WriteLine();

            Console.WriteLine("PreOrder traversal of BST in Recusrsive");
            TraversPreOrderRecursive(root);
            Console.WriteLine();

            Console.WriteLine("Preorder traversal of BST in Iterative");
            TraversPreorderIterative(root);
            Console.WriteLine();

            Console.WriteLine("PostOrder traversal of BST in Recusrsive");
            TraversPostrderRecursive(root);
            Console.WriteLine();

            Console.WriteLine("Postorder traversal of BST in Iterative");
            TraversPostorderIterative(root);
            Console.WriteLine();

            Console.WriteLine("BFS traversal of BST in Recusrsive");
            TraversBFSRecursive(root);
            Console.WriteLine();

            Console.WriteLine("Reverse Level BFS traversal of BST in Recusrsive");
            ReverseTraversBFSRecursive(root);
            Console.WriteLine();

            Console.WriteLine("Count Half and Full Node in the Binary tree");
            CountHalfANDFULLNodeIN_BinaryTree(root);
            Console.WriteLine();

            bool result = IsBinaryTreeIdentical(root, root1);
            Console.WriteLine("Is tree is Identitcal =  {0}", result);

            Console.ReadKey();

            Console.WriteLine("");
            Console.WriteLine("Initiating delete operation : Enter any node to delete");
            int value = Convert.ToInt32(Console.ReadLine());
            TraversInorderRecursive(root, 1);
            DeleteNode(root, value);
            Console.WriteLine("After delete Inorder traversal of BST in Recusrsive");
            TraversInorderRecursive(root);
            Console.ReadKey();
        }

        private static void TraversPostorderIterative(Node root)
        {
            Stack<Node> stk = new Stack<Node>();
            Stack<Node> stk2 = new Stack<Node>();
            if (root == null)
            {
                return;
            }
            stk.Push(root);
            while (stk.Count > 0)
            {
                var temp = stk.Pop();
                stk2.Push(temp);
                if (temp.left != null)
                {
                    stk.Push(temp.left);
                }
                if (temp.right != null)
                {
                    stk.Push(temp.right);
                }
            }
            while(stk2.Count > 0)
            {
                Console.Write("{0}, ", stk2.Pop().value);
            }
        }

        private static void TraversPreorderIterative(Node root)
        {
            Stack<Node> stk = new Stack<Node>();
            if (root == null)
            {
                return;
            }
            stk.Push(root);
            while(stk.Count > 0)
            {
                var temp = stk.Pop();
                Console.Write("{0}, ", temp.value);
                if (temp.right != null)
                {
                    stk.Push(temp.right);
                }
                if (temp.left != null)
                {
                    stk.Push(temp.left);
                }
            }
        }

        private static Node TraversInorderIterative(Node root)
        {
            Stack<Node> stk = new Stack<Node>();
            if (root == null)
            {
                return root;
            }
            var current = root;
            var x = true;
            while (x)
            {
                if (current != null)
                {
                    stk.Push(current);
                    current = current.left;
                }
                else if (stk.Count > 0)
                {
                    var temp = stk.Pop();
                    Console.Write("{0}, ", temp.value);
                    if (temp.right != null)
                    {
                        current = temp.right;
                    }
                }
                else
                {
                    x = false;
                }
            }
            return root;
        }

        private static bool IsBinaryTreeIdentical(Node root, Node root1)
        {
            if (root != null && root1 == null || root1 != null && root == null)
            {
                return false;
            }
            Queue<Node> qu1 = new Queue<Node>();
            Queue<Node> qu2 = new Queue<Node>();
            var temp = root;
            var temp1 = root1;
            qu1.Enqueue(temp);
            qu2.Enqueue(temp1);
            while (qu1.Count > 0 && qu2.Count > 0)
            {
                if (temp.left != null)
                    qu1.Enqueue(temp.left);
                if (temp.right != null)
                    qu1.Enqueue(temp.right);
                temp = qu1.Dequeue();
                if (temp1.left != null)
                    qu2.Enqueue(temp1.left);
                if (temp1.right != null)
                    qu2.Enqueue(temp1.right);
                temp1 = qu2.Dequeue();
                if (temp.value != temp1.value)
                {
                    return false;
                }
            }
            return true;
        }

        private static void CountHalfANDFULLNodeIN_BinaryTree(Node root)
        {

            if (root == null) return;
            Queue<Node> que = new Queue<Node>();
            Node temp = root;
            int halfcount = 0;
            int fullnode = 0;
            while (temp != null)
            {
                if (temp != null)
                {
                    if ((temp.left != null && temp.right == null) || (temp.right != null && temp.left == null))
                    {
                        halfcount++;
                    }
                    else if (temp.left != null && temp.right != null)
                    {
                        fullnode++;
                    }
                }
                if (temp.left != null)
                    que.Enqueue(temp.left);
                if (temp.right != null)
                    que.Enqueue(temp.right);
                if (que.Count > 0)
                {
                    temp = que.Dequeue();
                }
                else
                {
                    temp = null;
                }
            }
            Console.WriteLine("Total Half Node in binary Tree is {0} and fill node is {1}", halfcount, fullnode);
        }

        private static void ReverseTraversBFSRecursive(Node root)
        {
            if (root == null) return;
            Queue<Node> que = new Queue<Node>();
            Stack<Node> stack = new Stack<Node>();
            Node temp = root;
            stack.Push(temp);
            while (temp != null)
            {
                if (temp.right != null)
                {
                    que.Enqueue(temp.right);
                }
                if (temp.left != null)
                {
                    que.Enqueue(temp.left);
                }
                if (que.Count > 0)
                {
                    temp = que.Dequeue();
                    if (temp != null)
                    {
                        stack.Push(temp);
                    }
                }
                else
                {
                    temp = null;
                }
            }

            while (stack.Count > 0)
            {
                Console.Write("{0} ", stack.Pop().value);
            }
        }

        private static void TraversBFSRecursive(Node root)
        {
            if (root == null) return;
            Queue<Node> que = new Queue<Node>();
            Node temp = root;
            while (temp != null)
            {
                Console.Write("{0} ", temp.value);
                if (temp.left != null)
                    que.Enqueue(temp.left);
                if (temp.right != null)
                    que.Enqueue(temp.right);
                if (que.Count > 0)
                {
                    temp = que.Dequeue();
                }
                else
                {
                    temp = null;
                }
            }
        }

        private static Node DeleteNode(Node root, int value)
        {
            if (root == null) return root;
            if (value < root.value)
            {
                root.left = DeleteNode(root.left, value);
            }
            else if (value > root.value)
            {
                root.right = DeleteNode(root.right, value);
            }
            else
            {
                if (root.left == null) return root.right;
                else if (root.right == null) return root.left;
                else
                {
                    root.value = minValue(root.right);
                    root.right = DeleteNode(root.right, root.value);
                }
            }
            return root;

        }

        private static int minValue(Node root)
        {
            int minv = root.value;
            while (root.left != null)
            {
                minv = root.left.value;
                root = root.left;
            }
            return minv;
        }

        private static void TraversPostrderRecursive(Node root, int? isLogFalse = null)
        {
            if (root == null)
            {
                return;
            }
            TraversPostrderRecursive(root.left, isLogFalse);
            TraversPostrderRecursive(root.right, isLogFalse);
            if (isLogFalse == null)
                Console.Write("{0}, ", root.value);
        }

        private static void TraversPreOrderRecursive(Node root, int? isLogFalse = null)
        {
            if (root == null)
            {
                return;
            }
            if (isLogFalse == null)
                Console.Write("{0}, ", root.value);
            TraversPreOrderRecursive(root.left, isLogFalse);
            TraversPreOrderRecursive(root.right, isLogFalse);
        }

        public static Node InsertNode(Node root, int value)
        {
            if (root == null)
            {
                root = new Node(value);
                return root;
            }
            else if (root.value < value)
            {
                root.right = InsertNode(root.right, value);
            }
            else
            {
                root.left = InsertNode(root.left, value);
            }
            return root;

        }

        public static void TraversInorderRecursive(Node root, int? isLogFalse = null)
        {
            if (root == null)
            {
                return;
            }
            TraversInorderRecursive(root.left, isLogFalse);
            if (isLogFalse == null)
            {
                Console.Write("{0}, ", root.value);
            }
            TraversInorderRecursive(root.right, isLogFalse);
        }
    }

    public class Node
    {
        public Node(int val)
        {
            value = val;
        }
        public int value;
        public Node left;
        public Node right;
    }
}
