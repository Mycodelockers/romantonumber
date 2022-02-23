# romantonumber

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000

public static final int romanToInteger2(String s) {

	Map<Character, Integer> values = new LinkedHashMap<>();
	values.put('I', 1);
	values.put('V', 5);
	values.put('X', 10);
	values.put('L', 50);
	values.put('C', 100);
	values.put('D', 500);
	values.put('M', 1000);

	int number = 0;
	for (int i = 0; i < s.length(); i++) {
		if (i+1 == s.length() || values.get(s.charAt(i)) >= values.get(s.charAt(i + 1))) {
			number += values.get(s.charAt(i));
		} else {
			number -= values.get(s.charAt(i));
		}
	}
	return number;
}
