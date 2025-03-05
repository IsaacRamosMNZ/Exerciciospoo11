# Exerciciospoo11

CLASSE PRINCIPAl:

package sobreescrita;

public class Sobreescrita {

    public static void main(String[] args) {
 //     veiculo v1 = new veiculo(); Não é possivel instanciar classe abstrata
 Carro c1 = new Carro();
   c1.setModelo("Fusca");
        System.out.println("Carro:" + c1.getModelo());
        c1.mover();
        c1.exibir();
        
        Motocicleta m1 = new Motocicleta();
        m1.setModelo("MT03");
        System.out.println("Moto" + m1.getModelo());
        m1.mover();
        m1.exibir();

    }
   
}




2:package sobreescrita;

package sobreescrita;


public abstract class veiculo {
private String modelo;

public void mover(){
    System.out.println("O veiculo esta se movendo");  
    
    
  }   

    public String getModelo() {
        return modelo;
    }

    public void setModelo(String modelo) {
        this.modelo = modelo;
    }
 public void exibir(){
     
 }
  public  void abstecimento(){
      
  }

}




3:package sobreescrita;

public class Carro extends veiculo{
    
    @Override
    public void mover(){
        System.out.println("O carro esta se movendo!");
        
    }
    @Override
   public void exibir (){
            System.out.println("Carro esta ligado!");
   } 
   public void abastecimento(){
       System.out.println("Motocicleta abastecido!");
   }
 }

4:

package sobreescrita;

public class Motocicleta extends veiculo{
    
    @Override
    public void mover(){
        System.out.println("A motocicleta esta se movendo!");
    }
    @Override
 public void exibir(){
     System.out.println("A motocicleta esta ligada!");
    
     
 }
    
}




        // Testando os métodos sobrecarregados
        System.out.println("Multiplicação de dois inteiros: " + calc.multiplicar(4, 5));
        System.out.println("Multiplicação de três inteiros: " + calc.multiplicar(2, 3, 4));
        System.out.println("Multiplicação de dois números decimais: " + calc.multiplicar(2.5, 3.2));
    }
}

package sobrecarga;

public class Calculadora {
    
    // Multiplicação de dois números inteiros
    public int multiplicar(int a, int b) {
        return a * b;
    }

    // Multiplicação de três números inteiros
    public int multiplicar(int a, int b, int c) {
        return a * b * c;
    }

    // Multiplicação de dois números decimais (double)
    public double multiplicar(double a, double b) {
        return a * b;
    }
}




3:package polimorfismo;

public class Main {
    public static void main(String[] args) {
        // Criando um array de animais
        Animal[] animais = new Animal[2];

        // Instanciando subclasses e armazenando no array
        animais[0] = new Cachorro();
        animais[1] = new Gato();1 package heranca;

public class Main {
    public static void main(String[] args) {
        // Criando um objeto da classe Aluno
        Aluno aluno1 = new Aluno("Carlos Silva", 20, "2024001");

        // Exibindo as informações do aluno
        aluno1.exibirInformacoes();
    }
}





secundaria package heranca;

public class Pessoa {
    protected String nome;  // Pode ser acessado por subclasses
    private int idade;      // Apenas acessível dentro da própria classe

    // Construtor
    public Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    // Getter para idade
    public int getIdade() {
        return idade;
    }

    // Método para exibir informações
    public void exibirInformacoes() {
        System.out.println("Nome: " + nome);
        System.out.println("Idade: " + getIdade());
    }
}

subclasse
package heranca;

public class Aluno extends Pessoa {
    private String matricula;

    // Construtor da classe Aluno
    public Aluno(String nome, int idade, String matricula) {
        super(nome, idade); // Chama o construtor da superclasse (Pessoa)
        this.matricula = matricula;
    }

    // Método para exibir as informações do aluno
    @Override
    public void exibirInformacoes() {
        super.exibirInformacoes(); // Chama o método da superclasse
        System.out.println("Matrícula: " + matricula);
    }
}





2:package sobrecarga;

public class Main {
    public static void main(String[] args) {
        // Criando um objeto da classe Calculadora
        Calculadora calc = new Calculadora();


        // Chamando o método emitirSom() para cada animal
        for (Animal animal : animais) {
            animal.emitirSom();
        }
    }
}

classe abstrata:package polimorfismo;

public abstract class Animal {
    // Método abstrato que será implementado pelas subclasses
    public abstract void emitirSom();
}

subclasse:package polimorfismo;

public class Gato extends Animal {
    @Override
    public void emitirSom() {
        System.out.println("O gato mia: Miau!");
    }
}



4;package heranca;

public class Main {
    public static void main(String[] args) {
        // Criando um objeto da classe Veiculo
        Veiculo veiculo1 = new Veiculo(180);
        veiculo1.descrever();
        veiculo1.descrever("Carro esportivo de alta performance.");

        System.out.println("--------------------------");

        // Criando um objeto da classe Moto
        Moto moto1 = new Moto(220, 600);
        moto1.descrever();
        moto1.descrever("Moto esportiva para competições.");
    }
}

secundaria:package heranca;

public class Veiculo {
    protected int velocidadeMaxima; // Pode ser acessado pela subclasse

    // Construtor
    public Veiculo(int velocidadeMaxima) {
        this.velocidadeMaxima = velocidadeMaxima;
    }

    // Método sobrecarregado: versão sem parâmetros
    public void descrever() {
        System.out.println("Velocidade máxima do veículo: " + velocidadeMaxima + " km/h");
    }

    // Método sobrecarregado: versão com parâmetro
    public void descrever(String descricao) {
        System.out.println("Velocidade máxima: " + velocidadeMaxima + " km/h. " + descricao);
    }
}

subclasse:package heranca;

public class Moto extends Veiculo {
    private int cilindradas; // Atributo específico da Moto

    // Construtor da classe Moto
    public Moto(int velocidadeMaxima, int cilindradas) {
        super(velocidadeMaxima); // Chama o construtor da superclasse (Veiculo)
        this.cilindradas = cilindradas;
    }

    // Sobrescrita do método descrever() sem parâmetros
    @Override
    public void descrever() {
        System.out.println("Esta é uma moto com " + cilindradas + " cilindradas.");
        System.out.println("Velocidade máxima da moto: " + velocidadeMaxima + " km/h");
    }
}



5:classe principal:package formas;

public class Main {
    public static void main(String[] args) {
        // Criando um círculo e definindo dimensões usando sobrecarga
        Circulo circulo = new Circulo("Vermelho");
        circulo.definirDimensoes(5);
        System.out.println("Área do Círculo: " + circulo.calcularArea() + " cm²");

        System.out.println("--------------------------");

        // Criando um retângulo e definindo dimensões
        Retangulo retangulo = new Retangulo("Azul");
        retangulo.definirDimensoes(4, 6);
        System.out.println("Área do Retângulo: " + retangulo.calcularArea() + " cm²");
    }
}


classe abstrata:package formas;

public abstract class Forma {
    protected String cor; // Atributo protegido para acesso nas subclasses

    // Construtor
    public Forma(String cor) {
        this.cor = cor;
    }

    // Método abstrato para calcular área (deve ser implementado pelas subclasses)
    public abstract double calcularArea();
}

subclasse:package formas;

public class Circulo extends Forma {
    private double raio; // Atributo privado

    // Construtor
    public Circulo(String cor) {
        super(cor);
    }

    // Método sobrecarregado: define raio com um inteiro
    public void definirDimensoes(int raio) {
        this.raio = raio;
        System.out.println("Raio definido como (int): " + raio + " cm");
    }

    // Método sobrecarregado: define raio com um número decimal
    public void definirDimensoes(double raio) {
        this.raio = raio;
        System.out.println("Raio definido como (double): " + raio + " cm");
    }

    // Implementação do método abstrato calcularArea()
    @Override
    public double calcularArea() {
        return Math.PI * raio * raio;
    }
}

subclassepackage formas;

public class Retangulo extends Forma {
    private double largura;
    private double altura;

    // Construtor
    public Retangulo(String cor) {
        super(cor);
    }

    // Método para definir dimensões do retângulo
    public void definirDimensoes(double largura, double altura) {
        this.largura = largura;
        this.altura = altura;
        System.out.println("Dimensões do retângulo definidas: " + largura + " x " + altura + " cm");
    }

    // Implementação do método abstrato calcularArea()
    @Override
    public double calcularArea() {
        return largura * altura;
    }
}


