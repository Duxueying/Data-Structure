import sun.swing.StringUIClientPropertyKey;

import java.util.ArrayList;
import java.util.List;
import java.util.Stack;

public class Tree {
    public static Node buildTree() {
        Node n1 = new Node(1);
        Node n2 = new Node(2);
        Node n3 = new Node(3);
        Node n4 = new Node(4);
        Node n5 = new Node(5);
        Node n6 = new Node(6);

        n1.left = n2; n1.right = n3;
        n2.left = n4;
        n3.left = n5; n3.right = n6;

        return n1;
    }
    public static void preorder(Node root) {
        Stack<Node> stack = new Stack<>();
        Node cur = root;
        while (cur != null || !stack.isEmpty()) {
            while (cur != null) {
                System.out.println(cur.val);
                stack.push(cur);
                cur = cur.left;
            }
            Node top = stack.pop();
            cur = top.right;
        }
    }
    public static void inorder(Node root) {
        Stack<Node> stack = new Stack<>();
        Node cur = root;
        while (cur != null || !stack.isEmpty()) {
            while (cur != null) {
                stack.push(cur);
                cur = cur.left;
            }
            Node top = stack.pop();
            System.out.println(top.val);
            cur = top.right;
        }
    }
    public static void postorder(Node root) {
        Stack<Node> stack = new Stack<>();
        Node cur = root;
        Node last = null;   // 上次被遍历完的结点
        while (cur != null || !stack.isEmpty()) {
            while (cur != null) {
                stack.push(cur);
                cur = cur.left;
            }
            Node top = stack.peek();
            if (top.right == null || top.right == last) {
                System.out.println(top.val);
                stack.pop();
                last = top;
            } else {
                cur = top.right;
            }
        }
    }

    public List<Integer> preorderTraversal(Node root) {
        List<Integer> list = new ArrayList<>();
        Stack<Node> stack = new Stack<>();
        Node cur = root;
        while (cur != null || !stack.isEmpty()) {
            while (cur != null) {
                list.add(cur.val);
                stack.push(cur);
                cur = cur.left;
            }

            Node top = stack.pop();
            cur = top.right;
        }

        return list;
    }

    public static void main(String[] args) {
        Node root = buildTree();
        preorder(root);
        System.out.println("==================");
        inorder(root);
        System.out.println("==================");
        postorder(root);
    }
}
