```java
import java.util.HashMap;
    public int longestPalindrome(String s) {
        HashMap<Character, Integer> frequencyMap = new HashMap<>();
        for (char ch : s.toCharArray()) {
            frequencyMap.put(ch, frequencyMap.getOrDefault(ch, 0) + 1);
        }

        int length = 0;
        boolean hasOddFrequency = false;
        for (int count : frequencyMap.values()) {
            length += count / 2 * 2;
            if (count % 2 != 0) {
                hasOddFrequency = true;
            }
        }

        if (hasOddFrequency) {
            length++;
        }

        return length;
    }
