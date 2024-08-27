class twoStacks {
    int arr[] = new int[100];
    int top1 = -1;          // aage sa lega too -1 sa start karo
    int top2 = arr.length;  // picha sa dalega na array mai too size lena hai
    twoStacks() {
        for(int top1 = 0; top1 < top2; top1++){
             arr[top1] = -1;
        }
    }
    // Function to push an integer into the stack1.
    void push1(int x) {
        top1++;   // aage sa aage badhate jao
        arr[top1] = x;
    }
    // Function to push an integer into the stack2.
    void push2(int x) {
        top2--;    // pich sa dalna hai
        arr[top2] = x;
    }
    // Function to remove an element from top of the stack1.
    int pop1() {
        if(top1 == -1){
            return -1;
        }
        else return arr[top1--];
    }

    // Function to remove an element from top of the stack2.
    int pop2() {
        if(top2 == arr.length){
            return -1;
        }
        else return arr[top2++];
    }
}

