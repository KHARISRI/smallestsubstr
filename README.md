chars = 256

def max_dist_char(str, n): 
    count = [0] * chars 
    for i in range(n): 
        count[ord(str[i])] += 1
      
    max_dist = 0
    for i in range(chars): 
        if (count[i] != 0): 
            max_dist += 1    
      
    return max_dist 
  
def smallSubstr_maxDistChar(str): 
  
    n = len(str)     
    max_dist = max_dist_char(str, n) 
    minl = n    

    for i in range(n): 
        for j in range(n): 
            subs = str[i:j] 
            subs_length = len(subs) 
            sub_dist_char = max_dist_char(subs,subs_length) 
            if (subs_length < minl and 
                max_dist == sub_dist_char): 
                minl = subs_length 
  
    return minl 
  

if __name__ == "__main__": 
    str = input()
      
    l = smallSubstr_maxDistChar(str); 
    print(l)





    
