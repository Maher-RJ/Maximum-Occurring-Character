## Task & Solution


### Task
<img width="408" alt="maximum occurring character" src="https://user-images.githubusercontent.com/57875037/105993217-65947d80-60a6-11eb-9e48-53acba6b0537.png">

### Solution

```java
  
  public static char maximumOccurringCharacter(String text){
  
    Map<Character,Integer> maxOccurences = new HashMap<Character, Integer>();
    Character mostFreqChar = null ;
    
    if (text !=null && text.length()>0){
        char[] chars = text.toCharArray();
        for(char c : chars){
            // increase maxOccurences if exists
            if (maxOccurences.containsKey(c)){
                maxOccurences.put(c, maxOccurences.get(c)+1);
            // create an entry if not
            }else{
                maxOccurences.put(c, 1);
            }
        }
        
        // search for key with highest value
        int count = 0;
        for(Map.Entry<Character,Integer> entry : maxOccurences.entrySet()){
            if (entry.getValue() > count){
                mostFreqChar = entry.getKey();
                count = entry.getValue();
            }
        }
    }
    
    return mostFreqChar;
}

```

