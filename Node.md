class Node{
	String value;
	Node next;
	Node(String s){
		value = s;
		next = null;
	}
}
int n;
Node head = null;
if (str.length()==3){
	Node ptr = head;
	if (head==null) sb.append("/\n");
	while(ptr!=null){
		sb.append("/"+ptr.value + "\n");
		ptr = ptr.next;
	}
} else{
	str = str.subString(3,str.length());
	if (str.charAt(0)=='/') head = null;
	String [] s = str.split("/");
	for (int i=0; i<s.length; i++){
		if (head==null){
			head = new Node(s[i]);
		} else {
			Node ptr = head;
			while(ptr.next!=null)
				ptr = ptr.next;
			if (s.equals("..")) {
				ptr.next = null;
			} else {
				ptr.next = new Node(s[i]);
			}
		}
	}
}