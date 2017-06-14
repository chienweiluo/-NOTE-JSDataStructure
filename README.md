# JSDataStructure

## STACK

*Last In First Out 


        //implement
        
        function Stack(){
            var s =[]

            this.push = function(el){
                s.push(el)
            }

            this.pop = function(){
                return s.pop()
            }

            this.peek = function(){
                return s[s.length-1]
            }

            this.isEmpty = function(){
                if(s.length===0){
                    return true
                }
                else{
                    retrun false
                }
            }

            this.clear = function(){
                s= []
            }

            this.size = function(){
                return s.length
            }
            
            this.print = function(){
                console.log(s.toString())
            }

        }
        
        //unit test
        
        var stack = new Stack();  新增一個實例
        
        stack.push("Chien");

        stack.push("Wei");        

        stack.push("Luo's");

        stack.push("GitHub");
        
        stack.print() //Chien Wei Luo's GitHub
        
        stack.pop()
        
        stack.size(); //3
        
        stack.peek(); //"Luo's"
       
        stack.isEmpty(); //false
        
        stack.clear();
        
        
        
