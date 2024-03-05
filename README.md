# PunctuationCounter.java

import java.util.HashMap;
import java.util.Map;

public class PunctuationCounter {
    public static void main(String[] args) {
        String text = "Mary had a little lamb, her fleece was as white as snow, and everywhere Mary went, the lamb was sure to go. -that was a nice poem- the end.";

        Map<Character, Integer> punctuationCounts = countPunctuation(text);

        System.out.println("Punctuation Marks Counts:");
        System.out.println("========================");
        for (Map.Entry<Character, Integer> entry : punctuationCounts.entrySet())
            System.out.println(entry.getKey() + ": " + entry.getValue());
    }

    private static Map<Character, Integer> countPunctuation(String text) {
        Map<Character, Integer> punctuationCounts = new HashMap<>();
        String punctuationMarks = ",.-";

        for (char c : text.toCharArray()) {
            if (punctuationMarks.contains(String.valueOf(c))) {
                punctuationCounts.put(c, punctuationCounts.getOrDefault(c, 0) + 1);
            }
        }

        return punctuationCounts;
    }
}
