
    class Solution {
        public String removeOuterParentheses(String S) {
            Stack<Character> stack=new Stack<Character>();
            String str="";
            for(int i=0;i<S.length();i++){
                if(S.charAt(i)=='('){
                    if(!stack.isEmpty()) str+="(";
                    stack.push(S.charAt(i));
                } else {
                    stack.pop();
                    if(!stack.isEmpty()) str+=")";
                }
            }
            return str;
        }
    }
