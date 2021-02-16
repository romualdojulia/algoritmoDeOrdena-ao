# algoritmoDeOrdenacao
Exemplo das vídeo aulas sobre algoritmos de ordenação

//Aula 1//

class ExBubbleSort {
	
	public static void main(String[] args) {
		int vetor[] = {3, 6, 2, 1, 8,4};
		int aux;
		boolean controle;
	
		for(int i = 0; i<vetor.length; i++) {
			controle = true;
			for(int j=0; j<(vetor.length -1); j++) {
			
				if(vetor[j] > vetor[j+1]) {
					aux = vetor[j];
					vetor[j] = vetor[j+1];
					vetor[j+1] = aux;
					controle = false;
				}
			}
			if(controle) {
				break;
			}
		}
		
		for(int i = 0; i<vetor.length; i++) {
			System.out.println(vetor[i]+ "");
		}

	}
}

//Aula 2//

import java.util.Arrays;
import java.util.Random;

public class SelectionSort {

	public static void main(String[] args) {
		int []v = gerarVetor(10);
		selectionSort(v);
		System.out.println(Arrays.toString(v));
	}
	
	private static void selectionSort(int[]v) {
		for(int i=0; i<v.length; i++) {
			int menor  = i;
			for(int j = i+1; j<v.length; j++) {
				if(v[j] < v[menor])
					menor = j;
			}
			trocar(v, i, menor);
		}
	}

	private static void trocar(int []v, int i, int menor) {
		int aux = v[i];
		v[i] = v[menor];
		v[menor] = aux;
	}
	
	public static int [] gerarVetor(int n) {
		int []v = new int [n];
		Random gerador = new Random();
		for(int i = 0; i< n; i++) {
			v[i] = gerador.nextInt(100);
		}
		return v;
	}
}

//Aula 3//

public class Calculadora {

	public static int fatorialNaoRecursivo(int num) {
		
		if(num ==0) {
				return 1;
		}
		
		int total =1;
		for(int i=num; i>1;i--) {
			total *=i;
		}
		
		return total;
	}
	
	public static int fatorial(int num) {
		
		if(num ==0) {
			return 1;
		}
		
		return num * fatorial(num -1);
	}
}

public class TesteCalculadora {

	public static void main(String[] args) {
		
		int fatorialNR = Calculadora.fatorialNaoRecursivo(5);
		System.out.println(fatorialNR);
		
		int fatorialIR = Calculadora.fatorial(5);
		System.out.println(fatorialIR);
	}

}
