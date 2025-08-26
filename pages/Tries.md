tags:: #[[Data Structure and Algorithms]] #DSA #code
icon:: 🌴

-
-
- Tries is an important data structure specially use to search words and prefixes in O(k) time where k is the length of word
-
- [Code/github/nikneal91/javaCollections](vscode://file:///C:/Users/nikhilsharma03/Code/github/nikneal91/javaCollections)
- `Code block`
	- ```java
	   class TrieNode {
	       TrieNode[] children = new TrieNode[26]; // Children nodes
	       boolean isEnd; // Flag to represent the end of a word
	  
	       public TrieNode() {
	           isEnd = false;
	           for (int i = 0; i < 26; i++)
	               children[i] = null;
	       }
	   }
	  
	  public class Trie {
	      private TrieNode root;
	  
	      public Trie() {
	          root = new TrieNode();
	      }
	  
	      // Function to search a word in the Trie
	      public boolean search(String word) {
	          TrieNode node = root;
	          for (int i = 0; i < word.length(); i++) {
	              int index = word.charAt(i) - 'a';
	              if (node.children[index] == null)
	                  return false; // Word not found
	              node = node.children[index];
	          }
	          return node.isEnd; // Return true if word exists, false otherwise
	      }
	    
	     public boolean insert(String word) {
	       TrieNode node = root;
	       for (int i=0;i<word.length;i++) {
	         int index = word.chatAt(i)-'a';
	         if ( node.children[index] == null)
	             root.children[index] = new TrieNode();
	         root = root.children[index];
	       }
	       isEnd = true;
	     }
	  
	    public boolean startsWith(String prefix) {
	      TrieNode node = root;
	      for (char ch : prefix.toCharArray()) {
	        int index = ch-'a';
	        if ( node.children[index] == null ) 
	          	return false;
	        node = node.children[index];
	      }
	      return true;
	    }
	    
	  }
	  
	  ```
		-
- add some data here
-
-