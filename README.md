
# Ruby
- Versão atual 2.4.1: https://www.ruby-lang.org/en/
- Nos exemplos abaixo utilizaremos o *ruby 2.3.4*
- Como ver a versão de Ruby atual: `ruby -v`
- Instale o RVM para gerenciar as versões do ruby: https://rvm.io/
- Como instalar o Jupyter notebook com kernel Ruby: https://github.com/SciRuby/iruby#mac

Os códigos podem ser executados no terminal interativo do ruby, IRB, sem necessidade de instalar/configurar o Anaconda e Jupyter Notebook. Para tanto, digite `irb` no seu terminal para iniciar o interpretador.

**Imprimindo no console:**


```ruby
puts "Olá!"
puts "1"
puts 1
puts [1,3,"string"]
```

**A função `print` funciona de forma similar, mas não colocar o `\n` ao final:**


```ruby
print "Olá!"
print "1"
print 1
print [1,3,"string"]
```

**A função `p` já utiliza o inspect, sendo mais interessante para inspecionar o valor de uma variável, por exemplo:**


```ruby
p "1"
p 1
p [1,3,"string"]
```

**Todo objeto em ruby possui a função `methods`:**


```ruby
2.methods
```

**E tudo em ruby é um objeto 😝**


```ruby
1.class
```


```ruby
"1".class
```


```ruby
puts 1.class
puts 1.class.superclass
puts 1.class.superclass.superclass
```


```ruby
true.class
```


```ruby
false.class
```

# 😱


```ruby
nil.class
```

**Porque isso é fodástico!? Porque torna tudo muito simples e flexível!**

**É possível fazer coisas como:**


```ruby
2.times { print "G" }
```


```ruby
1.upto(10) {|number| print number }
```


```ruby
10.downto(1) {|x| print x}
```


```ruby
3.step(45, 5) {|x| puts x}
```


```ruby
string_lindamente_flexivel = "Gol, " * 4 + "Gooooooooollllllllll"
```


```ruby
string_lindamente_flexivel.reverse
```

**String contém os métodos downcase, capitalize, upcase... Para saber mais, vá na documentação ou utilize o método `methods`:**


```ruby
"string".methods
```

### Iterações: Range (invervalos), Array, interpolação de strings:


```ruby
bla = []
for i in (3..7) do 
  bla << "iterando #{i}".upcase
end

bla.join(", ")
```


```ruby
array1 = ["hello", "this", "is", "an", "array!"]
array2 = []
array2 << array1.pop until array1.empty?

p array1
p array2
```


```ruby
array1 = array2.reverse

p array1
p array2
```

**Por convensão, métodos com ! causam uma mudança permanente ou potenciosamente perigosa, por exemplo aplicar a mudança ao próprio objeto ao invés de retornar um novo objeto.**


```ruby
p array1
array1.reverse!
p array1
```

**Métodos com ? retornam um booleano (também é apenas uma convensão)**


```ruby
a = ""
puts "string vazia" if a.empty?
```

## Hash


```ruby
hash = { :goleira => "Maria", :atacante => "Marta", :zagueira => "Mariane"}
hash.each do |key, value|
  puts value
end
```

## Classes


```ruby
class MinhaClasse
  attr_accessor :hora_do_silvio # attr_reader

  def initialize
    puts "no construtor..."
    
    self.hora_do_silvio = "Olá default"
    @momento_construtor = Time.now
  end
  
  def atualiza_hora_do_silvio
    self.hora_do_silvio = "Má ôi.. são #{@momento_construtor}"
  end
  
  def to_s
    # objeto Cumprimentador num formato bonito 
    "objeto de MinhaClasse {#{self.hora_do_silvio}}"
  end
end

olar = MinhaClasse.new
puts olar
```


```ruby
olar.hora_do_silvio
```


```ruby
olar.atualiza_hora_do_silvio
```


```ruby
class OutraClasse < MinhaClasse
  @@atributo_estatico = "Valor estatico"
  
  def to_s
    "objeto de OutraClasse chamando #{metodo_privado}"
  end
  
  def self.puts_metodo_estatico
    puts "Valor do atributo estatico: #{@@atributo_estatico}"
  end
  
  protected
  def metodo_protected
    
  end
  
  def outro_medodo_protected
    
  end
  
  private 
  def metodo_privado
    "metodo privado"
  end
end

outro_objeto = OutraClasse.new
puts outro_objeto
```


```ruby
outro_objeto.atualiza_hora_do_silvio
```


```ruby
OutraClasse.puts_metodo_estatico
```

## ActiveSupport


```ruby
require 'active_support'
require 'active_support/core_ext'
```

**Numeric e Integer**


```ruby
puts 2.kilobytes   # => 2048
puts 1.megabytes 
```


```ruby
puts 8.multiple_of?(2)
puts 3.multiple_of?(4)
```


```ruby
puts 1.ordinal
puts 2.ordinal
```

**Time e Datetime**


```ruby
puts 1.month.from_now
 
puts 2.years.from_now
 
# equivalente a Time.current.advance(months: 4, years: 5)
puts (4.months + 5.years).from_now
```


```ruby
hoje = Time.now
puts "Ontem foi dia #{hoje.yesterday.day}"
```

**Array**


```ruby
t = ["AAA", "BBB", "CCC", "DDD"]
puts t.third
puts t.first
```


```ruby
t.in_groups_of(2) do |a, b|
  puts "a: #{a}, b: #{b}"
end
```

**Range**


```ruby
puts (1..10).include?(3..7)  
puts (1..10).include?(0..7)  
puts (1..10).include?(3..11) 
```

## Próximos passos
- Path de Ruby com 10 cursos: https://www.codeschool.com/learn/ruby
- Rails!!



```ruby

```
