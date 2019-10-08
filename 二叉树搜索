public class BinarySearchTree {
    public static class Node {
        int key;
        Node left;
        Node right;

        public Node(int key) {
            this.key = key;
        }
    }

    private Node root = null;

    /**
     * 在搜索树中查找 key，如果找到，返回 key 所在的结点，否则返回 null
     * @param key
     * @return
     */
    public Node search(int key) {
        Node cur = root;
        while (cur != null) {
            if (key == cur.key) {
                return cur;
            } else if (key < cur.key) {
                cur = cur.left;
            } else {
                cur = cur.right;
            }
        }

        return null;
    }

    /**
     * 插入
     * @param key
     * @return true 表示插入成功, false 表示插入失败
     */
    public boolean insert(int key) {
        if (root == null) {
            root = new Node(key);
            return true;
        }

        Node cur = root;
        Node parent = null;
        while (cur != null) {
            if (key == cur.key) {
                return false;
            } else if (key < cur.key) {
                parent = cur;
                cur = cur.left;
            } else {
                parent = cur;
                cur = cur.right;
            }
        }

        Node node = new Node(key);
        if (key < parent.key) {
            parent.left = node;
        } else {
            parent.right = node;
        }
        return true;
    }

    /**
     * 删除成功返回 true，失败返回 false
     * @param key
     * @return
     */
    public boolean remove(int key) {
        Node cur = root;
        Node parent = null;
        while (cur != null) {
            if (key == cur.key) {
                // 找到，准备删除
                removeNode(parent, cur);
                return true;
            } else if (key < cur.key) {
                parent = cur;
                cur = cur.left;
            } else {
                parent = cur;
                cur = cur.right;
            }
        }

        return false;
    }

    private void removeNode(Node parent, Node cur) {
        if (cur.left == null) {
            if (cur == root) {
                root = cur.right;
            } else if (cur == parent.left) {
                parent.left = cur.right;
            } else {
                parent.right = cur.right;
            }
        } else if (cur.right == null) {
            if (cur == root) {
                root = cur.left;
            } else if (cur == parent.left) {
                parent.left = cur.left;
            } else {
                parent.right = cur.left;
            }
        } else {
            Node goatParent = cur;
            Node goat = cur.right;
            while (goat.left != null) {
                goatParent = goat;
                goat = goat.left;
            }

            cur.key = goat.key;
            //cur.value = goat.value;

            if (goat == goatParent.left) {
                goatParent.left = goat.right;
            } else {
                goatParent.right = goat.right;
            }
        }
    }

    public static void main(String[] args) {
        // 1. 创建搜索树
        // 2. 随机插入一些数据
        // 3. 打印前序 + 中序遍历
        // 4. 查找
        BinarySearchTree tree = new BinarySearchTree();
        int[] keys = { 3, 9, 7, 4, 1, 6, 2, 8, 5 };
        for (int key : keys) {
            System.out.println(tree.insert(key));
        }
        System.out.println("插入重复数据");
        System.out.println(tree.insert(7));

        System.out.println("前序遍历");
        preOrder(tree.root);
        System.out.println("中序遍历");
        inOrder(tree.root);

        System.out.println(tree.search(7).key);
        System.out.println(tree.search(8).key);
        System.out.println(tree.search(5).key);
    }

    private static void inOrder(Node node) {
        if (node != null) {
            inOrder(node.left);
            System.out.println(node.key);
            inOrder(node.right);
        }
    }

    private static void preOrder(Node node) {
        if (node != null) {
            System.out.println(node.key);
            preOrder(node.left);
            preOrder(node.right);
        }
    }
}
