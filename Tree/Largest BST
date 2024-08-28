class Solution{
    
   public static void inorder(Node root,ArrayList<Integer> list)
   {
       if(root==null) return;
       inorder(root.left,list);
       list.add(root.data);
       inorder(root.right,list);
   }
   public static boolean  validate( ArrayList<Integer> list)
   {
       for(int i=0;i<list.size()-1;i++)
       {
           if(list.get(i+1)<=list.get(i)) return false;
       }
       return true;
   }
    public static void traversal(Node root,int max[])
    {
        if(root==null) return ;
        ArrayList<Integer> list=new ArrayList<>();
        // int size[]={0};
        inorder(root,list);
       if( validate(list))
       {
         max[0]=(int )Math.max(max[0],list.size());  
       }
        traversal(root.left,max);
        traversal(root.right,max);
        
        
    }
    static int largestBst(Node root)
    {
        int max[]={0};
        traversal(root,max);
        return max[0];
        
        
    }
    
}
