import java.util.*;

public class Solution {
    public int[] beautifulArray(int n) {
        return generateBeautifulArray(n);
    }

    private int[] generateBeautifulArray(int n) {
        if (n == 1) {
            return new int[]{1};
        }
        List<Integer> oddList = new ArrayList<>();
        List<Integer> evenList = new ArrayList<>();
        for (int num : generateBeautifulArray((n + 1) / 2)) {
            oddList.add(2 * num - 1);
        }
        for (int num : generateBeautifulArray(n / 2)) {
            evenList.add(2 * num);
        }
        oddList.addAll(evenList);
        int[] result = new int[oddList.size()];
        for (int i = 0; i < oddList.size(); i++) {
            result[i] = oddList.get(i);
        }

        return result;
    }
}
