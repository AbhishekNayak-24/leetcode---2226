# leetcode---2226
Maximum Candices Allocated to K Children
//code in java
class Solution {
        public int maximumCandies(int[] candies, long k) {
                int low = 1, high = getMax(candies), result = 0;

                        while (low <= high) {
                                    int mid = low + (high - low) / 2;
                                                if (canDistribute(candies, k, mid)) {
                                                                result = mid;  // Try a larger value
                                                                                low = mid + 1;
                                                                                            } else {
                                                                                                            high = mid - 1;
                                                                                                                        }
                                                                                                                                }
                                                                                                                                        return result;
                                                                                                                                            }

                                                                                                                                                private int getMax(int[] candies) {
                                                                                                                                                        int max = 0;
                                                                                                                                                                for (int candy : candies) {
                                                                                                                                                                            max = Math.max(max, candy);
                                                                                                                                                                                    }
                                                                                                                                                                                            return max;
                                                                                                                                                                                                }

                                                                                                                                                                                                    private boolean canDistribute(int[] candies, long k, int perChild) {
                                                                                                                                                                                                            long count = 0;
                                                                                                                                                                                                                    for (int candy : candies) {
                                                                                                                                                                                                                                count += (candy / perChild);  // Count how many children can receive `perChild` candies
                                                                                                                                                                                                                                        }
                                                                                                                                                                                                                                                return count >= k;
                                                                                                                                                                                                                                                    }
                                                                                                                                                                                                                                                    }
