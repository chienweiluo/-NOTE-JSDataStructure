# JSDataStructure

## QUEUE/PRIORITY QUEUE

*First in First Out

*增刪元素發生在不同端

*priority queue: 不一定遵循FIFO, e.g VIP先處理, 優先值如果一樣就照順序


### QUEUE 佇列

    function Queue(){
        q =[]
        this.enqueue = function(el){
            q.push(el)
        }

        this.dequeue = function(){
            return q.shift()
        }

        this.front = function(){
            return q[0]
        }

        this.isEmpty = function(){
            if(q.length ==0){
            return true}
            else{
            return false}
        }

        this.size = function(){
            return q.length
        }

        this.print = function(){
            console.log(q.toString())
        }
    }

### Priority Queue 優先級佇列

    function PriorityQueue(){
        let q = []
        function QueueEl(el,priority){
            this.el = el
            this.priority = priority
        }

        this.enqueue = function(item, pri){
            const queueElement = new QueueEl(el,pri)

            if(this.isEmpty){
                q.push(queueElement);
            }
            else{
                let add = false
                for(i=0, i<this.length, i++){
                    if(queueElement.priority <q[i]priority ){
                        q.splice(i, 0, queueElement)
                    }
                    add = true
                }

                if(!add){
                    q.push(queueElement)
                }
            }
        }

        this.dequeue = function(){
            return q.shift()
        }

        this.front = function(){
            return q[0]
        }

        this.isEmpty = function(){
            return q.length ==0
        }

        this.size = function(){
            return q.length
        }

        this.print = function(){
            console.log(JSON.Stringfy(q)) 
        }
    }
