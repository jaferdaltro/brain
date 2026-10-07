---
apple-notes-id: F602BA45-52C4-4BCB-9777-A136939B7031
---
- Fazendo extend self os métodos são de classe
	

```
class Calc
  extend self // class << self
  
  def add(a, b)
     a + b
  end

  def sub(a, b)
    a - b
  end
end

```