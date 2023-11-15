# Find-the-Duplicate-number-using-Java-Leetcode
    
    class Solution {
        public static void sort(int[] arr){
            int i = 0;
            while(i<arr.length){
                int correct = arr[i]-1;
                if(i<arr.length && arr[i] != arr[correct]){
                    swap(arr,i,correct);
                }else{
                    i++;
                }
            }
        }
        public static void swap(int[] arr, int i,int correct){
            int temp;
            temp = arr[i];
            arr[i] = arr[correct];
            arr[correct] = temp;
        }
        public static int duplicate(int[] arr){
            for(int i =0; i<arr.length;i++){
                if(i+1 != arr[i]){
                    return arr[i];
                }
            }
            return 0;
        }
        public int findDuplicate(int[] nums) {
            Solution obj = new Solution();
            obj.sort(nums);
            int result = obj.duplicate(nums);
            return result;
        }
    }
