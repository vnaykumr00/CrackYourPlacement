class Node{
    Node links[] = new Node[26];
    boolean flag = false;

    public Node(){

    }

    boolean containsKey(char ch){
        return (links[ch - 'a']!=null);
    }
    Node get(char ch){
        return links[ch - 'a'];
    }
    void put(char ch,Node node){
        links[ch - 'a'] = node;
    }
    void setEnd(){
        flag = true;
    }
    boolean isEnd(){
        return flag;
    }
}
class Trie {
    Node root;

    public Trie() {
        root = new Node();
    }
    
    public void insert(String word) {
        Node node = root;
        for(int i=0;i<word.length();i++){
            if(!node.containsKey(word.charAt(i))){
                node.put(word.charAt(i),new Node());
            }
            node = node.get(word.charAt(i));
        }
        node.setEnd();
    }
    
    public boolean search(String word) {
        Node node = root;

        for(int i=0;i<word.length();i++){
            if(!node.containsKey(word.charAt(i))){
                return false;
            }
            node = node.get(word.charAt(i));
        }
        if(node.isEnd()){
            return true;
        }
        return false;
    }
    
    public boolean startsWith(String prefix) {
        Node node = root;

        for(int i=0;i<prefix.length();i++){
            if(!node.containsKey(prefix.charAt(i))){
                return false;
            }
            node = node.get(prefix.charAt(i));
        }
        return true;
    }
    private void collectWords(Node node, String prefix, ArrayList<String> result) {
        if (node.isEnd()) {
            result.add(prefix);
        }
        for (char ch = 'a'; ch <= 'z'; ch++) {
            if (node.containsKey(ch)) {
                collectWords(node.get(ch), prefix + ch, result);
            }
        }
    }

    public ArrayList<String> getWordsStartingWith(String prefix) {
        ArrayList<String> result = new ArrayList<>();
        Node node = root;
        for (int i = 0; i < prefix.length(); i++) {
            if (!node.containsKey(prefix.charAt(i))) {
                return result;
            }
            node = node.get(prefix.charAt(i));
        }
        collectWords(node, prefix, result);
        return result;
    }
}
class Solution{
    static ArrayList<ArrayList<String>> displayContacts(int n, 
                                        String contact[], String s)
    {
        Trie trie = new Trie();
        for(int i = 0;i<contact.length;i++){
            trie.insert(contact[i]);
        }
        
        ArrayList<ArrayList<String>> ans = new ArrayList<>();
        
        for (int i = 1; i <= s.length(); i++) {
            String prefix = s.substring(0, i);
            ArrayList<String> matchedContacts = trie.getWordsStartingWith(prefix);
            Collections.sort(matchedContacts);
            if (matchedContacts.isEmpty()) {
                matchedContacts.add("0");
            }
            ans.add(matchedContacts);
        }

        return ans;
    }
}

