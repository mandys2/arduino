# arduino-Termômetro

Esse é um projeto feito por Amanda Castro de Melo, estudante do terceiro ano do ensino médio técnico em informática e com um curso extracurricular de arduino, fornecido pela própria instituição de ensino Senac Sorocaba no ano de 2022.

<hr>

Esse curso começou no segundo semestre de 2022, tendo aulas quinzenalmente fora do horário escolar às quartas-feiras. Foi um curso bem diferente e bem dinâmico, na qual desde o primeiro dia já tivemos contato com o kit de arduino e não teve tanta parte teórica, o que eu achei muito bom pois consigo aprender melhor na prática. Para as aulas usamos o Kit Iniciante V7 para arduino da RoboCore, achei que ele é um kit bem completo e fácil de manusear.
Ao longo das aulas fizemos vários códigos, mas o que mais me chamou a atenção e sendo o que eu mais gostei de fazer programar foi o termômetro.

<hr>

O termômetro de arduino basicamente funciona como um termômetro digital a onde tem sensores que quando atingem uma certa temperatura aciona um "alarme" e mostrando no visor que atingiu a temperatura máxima dos sensores.

 <hr>
 
 Circuito
 
 ![Termômetro-arduino](https://user-images.githubusercontent.com/112094909/204887536-79e20418-e05f-4d61-a689-c8c3c1c6526c.PNG)

<hr>

# Programação

    const int LM35 = 0;
		float temperatura = 0;
		int ADClido = 0;
		const int Buzzer = 12;
		const int LED[] = {2,3,4,5,6,7,8,9,10,11};
		
		void setup(){
			analogReference(INTERNAL); 
			pinMode(Buzzer, OUTPUT);
			for(int x = 0; x < 10; x++){
				pinMode(LED[x], OUTPUT);
			}
		}
		
		void loop(){
			ADClido = analogRead(LM35);
			temperatura = ADClido * 0.1075268817204301; 
			if(temperatura > 23.50){
				digitalWrite(LED[0], HIGH);
			}
			else{
				digitalWrite(LED[0], LOW);
			}
			if(temperatura > 24.00){
				digitalWrite(LED[1], HIGH);
			}
			else{
				digitalWrite(LED[1], LOW);
			}
			if(temperatura > 24.50){
				digitalWrite(LED[2], HIGH);
			}
			else{
				digitalWrite(LED[2], LOW);
			}
			if(temperatura > 25.00){
				digitalWrite(LED[3], HIGH);
			}
			else{
				digitalWrite(LED[3], LOW);
			}
			if(temperatura > 25.50){
				digitalWrite(LED[4], HIGH);
			}
			else{
				digitalWrite(LED[4], LOW);
			}
			if(temperatura > 26.00){
				digitalWrite(LED[5], HIGH);
			}
			else{
				digitalWrite(LED[5], LOW);
			}
			if(temperatura > 26.50){
				digitalWrite(LED[6], HIGH);
			}
			else{
				digitalWrite(LED[6], LOW);
			}
			if(temperatura > 27.00){
				digitalWrite(LED[7], HIGH);
			}
			else{
				digitalWrite(LED[7], LOW);
			}
			if(temperatura > 27.50){
				digitalWrite(LED[8], HIGH);
			}
			else{
				digitalWrite(LED[8], LOW);
			}
			if(temperatura > 28.00){
				digitalWrite(LED[9], HIGH);
				tone(Buzzer,2000);
			}
			else{
				digitalWrite(LED[9], LOW);
				noTone(Buzzer);
			}
		}
