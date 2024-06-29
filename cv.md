# *Oleg Deviatovski*
### Beginner Java Developer
***
## Contacts:
* Novopolotsk, BELARUS
* +375 29 8911237
* olegwsandroid@gmail.com

***
## Education:
Polotsk State University, Civil and industrial engineering

***
## Languages:
* Russian - Native
* English - Intermediate
* French - Intermediate

***
## Code example
```
Java class to check Name Surname similarity to avoid duplicates of persons

public class SurnameNameSimilarity {
    public static double calculateSimilarity(String str1, String str2) {
        int distance = levenshteinDistance(str1, str2);
        int maxLength = Math.max(str1.length(), str2.length());

        return 1.0 - (double) distance / maxLength;
    }

    private static int levenshteinDistance(String str1, String str2) {
        int[][] dp = new int[str1.length() + 1][str2.length() + 1];

        for (int i = 0; i <= str1.length(); i++) {
            for (int j = 0; j <= str2.length(); j++) {
                if (i == 0) {
                    dp[i][j] = j;
                } else if (j == 0) {
                    dp[i][j] = i;
                } else {
                    dp[i][j] = min(
                            dp[i - 1][j - 1] + costOfSubstitution(str1.charAt(i - 1), str2.charAt(j - 1)),
                            dp[i - 1][j] + 1,
                            dp[i][j - 1] + 1
                    );
                }
            }
        }

        return dp[str1.length()][str2.length()];
    }
```
