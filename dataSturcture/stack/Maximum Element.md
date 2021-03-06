PK
     ��J��1�,
  ,
     Maximum Element.md# Maximum Element

@(OJ)[hackerrank, datastructure]

> **Problem Information:**
>
> [problem's link](https://www.hackerrank.com/challenges/maximum-element)
>
> **AC date** : **2017-04-23**
>
> **Category** : data structure->stack


-------------------

## Question

You have an empty sequence, and you will be given  queries. Each query is one of these three types:

> 1 x  -Push the element x into the stack.
> 
> 2    -Delete the element present at the top of the stack.
> 
> 3    -Print the maximum element in the stack.

### Input Format

The first line of input contains an integer, $N$ . The next $N$ lines each contain an above mentioned query. (It is guaranteed that each query is valid.)

### Constraints


- $1 \le N \le 10^5$ 
- $1 \le x \le 10^5$ 
- $1 \le type \le 3$ 

### Output Format
For each type  query, print the maximum element in the stack on a new line.

### Sample Input

> 10
> 
> 1 97
> 
> 2
> 
> 1 20
> 
> 2
> 
> 1 26
> 
> 1 20
> 
> 2
> 
> 3
> 
> 1 91
> 
> 3



### Sample Output

> 26
>
> 91

## Answer

The most valuable part is the implementation of stack.
![Alt text](./1492937896023.png)


### C++

```c++

#head.h

using namespace std;

typedef struct Node{
    int data;
    Node * next;
}Node;

class Stack{
private:
    Node * top;
    int max;
    int findMax(Node *);
    void clear();
public:
    Stack();
    ~Stack();
    void push(int x);
    void pop();
    void printMax();
};

Stack::Stack():top(NULL), max(0){

}

Stack::~Stack(){
    clear();
}

void Stack::push(int x){
    Node * newTop = new Node;
    newTop->data = x;
    newTop->next = top;
    top = newTop;
    max = x > max? x:max;
}

void Stack::pop(){
    Node * temp = top;
    if(top->data==max){
        max = findMax(top->next);
    }
    top = top->next;
    free(temp);
}

void Stack::printMax(){
    cout<<max<<endl;
}

int Stack::findMax(Node * topItem){
    Node * temp = topItem;
    int tempMax = 0;
    while(temp!=NULL){
        tempMax = tempMax > temp->data?tempMax:temp->data;
        temp=temp->next;
    }
    return tempMax;
}

void Stack::clear(){
    while (top)
    {
        Node* topOfStack = top;
        top = top->next;
        delete topOfStack;

    }
}

int main() {
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */
    int N = 0;
    int type, x;
    Stack s;

    cin>>N;

    while(N--){
        cin >> type;
        if( type == 1 ){
            cin >> x;
            s.push(x);
        }
        else if( type == 2 ){
            s.pop();
        }
        else if( type == 3 )
            s.printMax();
    }
    return 0;
}



```
PK
     ��J���D�  �     1492937896023.png�PNG

   IHDR  �   �   �Z�  �IDATx��ylTU��{����Rd�(��p�P�k4Dc��`���ш�h\�AM�bP"C%Y!l�B�E�4-�[:o���s3,�����9���&M��{�=����o�2w2"�HD�@ @�z�L�{H@ @� �y  �  B;$��� � dC`�����+��춗���E�*�z��h��N��;vȉ'����k�gϞ2|�p=z�E�G﨩�����K�4�������＼<�ڵ�h[��	@ X���@�륵v|���2w�\���j�R�Ν���Ry�G�eN�<)o����\�R8����A;a��?��u�]ѻ�߿���L�2E�����bohhx�=i�$y��׼۱�p@ qB;q�[R�����i�Ju��g�y衇��~��u��g�ʚ5kd�����+��/z����,�s�I�׭q݂���?e��ݢo8z��}�ٹ@���v;�R1{�>}��o�wIgff��2?|��ߝaÆI����`�]�=z�����iy���?����6ƍ'C����J/`��566��/�,]�t���_Fo��<x��%�������ǎ��߰a����[�d��>n � $!���f�[���%R__ihh�~���"˖-����?k֬����yt~]N�E����2��ő�˗G�����=z42w��HFF�?oϞ=#��ٴiS$//���_|᭳��1RSS9t�P��_�dee��92RUU��@ ��8{<�7<������=f�?999�Vp��sss���������^�t�?�n}�X�B����Nl�۷����;ޱ�����'�D����CtݺU>`� y�7���љu�gΜ���o@ �$�$�R��㎝�]�n˖-r��qև~XƏ��}�y��w���~�{�Y�u�.�褻�����o@ ��	�ms
�\z�Yl�����߱��rl��G�bC?va�¾pڵk��%�_OB�c�L � �p"Z�V�P[[��Ow������;ލk��F���;���9����Kκv�Z��u����A�#a˗/?/�ǌ�Ǿ.�ǝ �@�����j	=��4\��+��b?�g�Ǟ1��{�'�o��}/X�@�Lu&@ ��x5M���bCZ�36��u<��)�k=v�z�e.�_�k���2q����� � 	
��� \X�ԩ��U݅�WB5j�߅74���������Ν;����]����~�ʈ#d�ȑ2y�d)**���� � I
�Iھ�7���ގn-��72}����޻w�l۶����֋�\jZ�x�̘1�R��>@ �7�jS�z-�~���]�ˊ������Џf���뢗3�N��v��9��߱�cw����m@ 3��WkZ�]�s�����g{?�������wV��6�'�/�ά���OF��7 �@��=��t��{�9Y�j��g�u������zJ�~�m��8�#]�U��-`�ӢE�d����wq@ ��v
�;jպ����{�1ټy��Z�&.��pғ��C4�@ �`��=�hWO.����:t�w,��W_�ѣG_rv�.�iӦy[��~<L?��u��l�;@ �	d�w�k���	TUU�������,o��I[&�=�W/�˓��_�����~զ~d+ޤWG�˚F�0�.QO��@ ����Mi@ #�7�J� � /@hoJ� �  ����( � �����" � Fm#�4�  �@�\\%x�д���ӯ�ԏp��n�ס)E �4 �Ӵ�:l���իW�~�[/��Wi�񃁡#�@(�P��L'�b)K�.�C��رc	m3̴� &�1��(�א^�T��v��aill� �1 �f�v�����ql�Ƹ^W�	@�nB����;@ |Bۧ� � v�vׇ�!�  ��>7@ �[�ж�>�@ _���)��  ��������w � ���O�@ � ����C @� �}
n �  `� �mw}� � � ��Sp@ �m��C�@ �m�� � �-@h�]z�  ��/@h��@ @�nB����;@ |Bۧ� � v�vׇ�!�  ��>��7"��������ǥ����;wNN�8!������z���@ ��vj�;t����RVV&.��������>ZZZd�����K/Iii�TUUuh�X ����/?s�"�[Ϻ%�q�F9{�����G222D�[�^�v��^�Zz��%�L � v	��mW=��&//O&N�(W]u�lݺU6m�$����[����n�:�y&M�$���F�B� � � ��o�%t�z�С2u�To�zŊ��m=�����z��L�"cǎ����Ў��#� �
ڮV6θ:w�,%%%2h� ٹs�TVVz���v~~��w�}�n�8�s7 �@
��bպ���}�=�H�nݼ����r�n��v����%;�SRQ։ \N�о����׭��ӧˈ#��t�}����3g���`��#@h�S�6�$���Ƕ�L���\�c�le���@ ���)aO�Juk{ڴi��v�~�����0&@ {8xiom��L��(�gϖ��
���8�mT��@ ��2"ѳ��o�B&��-�K��紋����h�ltH+B;��}�`���t˛	@�nv��]�#���@ 0ND���@ 0+@h���u@  ���!@ �
pL;A_=������JK��K&�SSS�wiR=V�M��ʒ��f6�ѵ>��~�{�k��x�+e�#��<�e���>�kp�yɹ$櫣��=zx����qk ��������_6o��d�����8�:uJ�o�ҫ�闀��"��Z�ؐ!Cd���W�Zԭ�����e���^Hj8������>/��>{���\���`S�9r�,Y�D


l�^�}!�$�`ܱc��}��2~�x+�Q��_��r�J5j�<���r�W���+Ab���#G�ȇ~(gΜ!�-����ҟy��y��!�5�KKKe˖-r�wȬY��S�Nh��ݛ�n�:�G�(�6�	VT_��$�nnJ��`Ӌ��ڵ�k���Hn��f�]}�k��X�j�C�X`�C@��nܸqּ����k֬�p�*�&L���?T���_5���4ωhI�떖M/���2��%���$�edQ}��d������.�<����'�K����h	��Ei@ C��!X�E @ hB;h�����@�}N򼴧a�	��
�@ �� �Ӧ�@ ��v�+H�@ �F��v�ԩ���c����9��2iF�� ��C@ ���!)�D @���1�  �@H��n"�  @h�@ @ $�vH
��nr奶J1#��:�9]�Bh�K�' �@��З� � �� ��.�f� � � �C_B�  �.�v�T�q"� �^��}	� �8>߃�H� �Ou�Z?��V= �������eh � n	�nՓ� � 8,@h;\\��  �� ��V= �����c������^�k����V�ж�t@ ���v|��  ��U��U�3 � � ����@ � ��*�A @ � ��&�����,�vX�k�;\���N:�D @ B;5�A @ �v
�Y% � �ډ�� � )�N�:Y% �.�s��IMM��L�n݄������ �*��3�
�p<�ӧO˗_~)MMMr뭷ʰaä��0:\{<e
M'	�Д���(�r�TEC��~���rY�l�̘1C�M�&C�	Mxw�kq]�cڮW�������n�o&s����~������}��<������֭[����[yf&/i�@�6�JcCBڇ��V�Ų��BZZZB:�Ļ�q��a9{���۷O4�ՄɌ��W_-s�̑�Çˊ+��nu_�j��������E�\�Č?��!@h�Q�P�����{������ɓiw<]w�777KUU�<��3����F(��NGE444xo���۷o����KYY��r�-�'�1!� ��Xe;�2�999ҥK�ڵkڅ�>t��(�]۹sg���w��d�p4�u��uuu~��o}����)���Kō � ӵ	}��5k��y�i�u������oY�x����2z�hv�|2hP=zT6n����ٻw�t��]F���?v��ٳ'-�@��i�m������~fV�u�cغ�ݯ_?�߿�2�����_䫯���;wz�<~�x/���^���R[[k�/� �T
ک�gݡ�㧺���fKy��!���d���2`� �9s�L�:����90*�oWmW+˸:D���,EEE2{�l��ɓ'ˠA��-�Y;kA�B۞Z��#гgOy��G��ꉏL�� ����g��H@O�#�CT0�jL����a@ � ����5@ �	��hi@ �`�`=i@ c��1ZF @ XB;XOZC @�� �m���@ V��֓�@ 0&@h��a@ � ����5@ �	��hi@ �`�`=i@ c��1ZF @ XB;XOZC @�� �m���@ V��֓�@ 0&@h��a@ � ����5@ �	��hi@ �`�`=i@ c��1ZF @ XB;XOZC @�� �m���@ V��֓�@ 0&@h��a@ � ����5@ �	��hi@ �`�`=i@ c��1ZF @ XB;XOZC @�� �m���@ V��֓�@ 0&@h��a@ � ����5@ �	��hi@ �`�$<#��dgg'�B�����Hf�K��m�[�#��55g�K ##Cl�K��2++˪��U��z��k�=�\�:�%E}�ر�����Yo���UCC��ݻW���ѣGe���RTT$��[�>��~}�sKK��X�x\�>*++eÆҷoߔ?��?��?�x��}��ɏ?�(�:u��v�ܶ1���mۼ�C��D����e�ĉ�i�&���l%��4�����P�;&�~�������,�y���1c�W�^������+���XJKK�٢mjj����r����|x�s���V���Z���5���4���2�v([]]��c��C_ ���ltwy��m�7pX�Y�܌�ף��Z���ͭ��-�>/���b����Cf��e�n�DCܥ��v���@�iNDs��@�%Bۥj2@ �m����@ \ �]�&cA pZ��v��@�%Bۥj2@ �m����@ \ �]�&cA pZ��v��@�%Bۥj2@ �m����@ \ �]�&cA pZ��v��@�%Bۥj2@ �m����@ \ �]�&cA pZ��v��@�%Bۥj2@ �m����@ \ �]�&cA pZ��v��@�%Bۥj2@ �m����@ \ �]�&cA pZ��v��@�%Bۥj2@ �m����@ \ �]�&cA pZ��v��@�%Bۥj2@ �m����@ \ �]�&cA pZ��v��@�%Bۥj2@ �m����@ \ �]�&cA pZ��v��@�%Bۥj2@ �m����@ \ �]�&cA pZ��v��@�%Bۥj2@ �m����@ \��,W. �6�    IEND�B`�PK 
     ��J��1�,
  ,
                   Maximum Element.mdPK 
     ��J���D�  �               \
  1492937896023.pngPK         �"    
