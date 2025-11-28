# STACK-HEAP-diagram


Follow the code below and build a step-by-step Stack-Heap Diagram.
Doing this exercise, it is okay to omit intermediate states (like the states in expressions evaluation, system methods calls, and so on); however, make sure to note changes when named variables are created or user-defined methods are called.

public class Main {
    public static void main(String[] args) {
        String name = "Kevin";
        List<String> list = new ArrayList<>();
        int times = 10;
        System.out.println(times + fill(list, name + name, times));
    }
    public static int fill(Collection<String> collection, String str, int times){
        String shrunk = shrink(str);
        times = (times + shrunk.length()) / 2;
        for (int i = 0; i < times / 2; i++) {
            collection.add(shrunk);
        }
        return times;
    }
    public static String shrink(String str){
        int newLength = str.length() / 2 + str.length() % 2;
        char[] chars = new char[newLength];
        for (int i = 0; i < str.length(); i+=2) {
            chars[i / 2] = str.charAt(i);
        }
        return new String(chars);
    }
}

How to self-evaluate this task

Please be aware that we expect the completed task to meet the following criteria:

Stack-Heap Diagram is drawn to depict how variables and objects reside in stack and heap memory segments of the JVM.
All primitive local variables and local references are depicted in the stack memory segment.
The stack memory segment shows the correct order of method calls and variables pushed to the stack.
All objects are depicted in the heap memory segment and properly linked to local references.
