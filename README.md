Programação do semaforo formula 1

const int prestage [] = {23,22}; 
const int numeroprestage = sizeof(prestage) / sizeof(int); 
const int stage [] = {21,19}; 
const int numerostage = sizeof(stage) / sizeof(int); 
const int laranjas [] = {18,5}; 
const int numeroslaranjas = sizeof(laranjas) / sizeof(int); 
const int orange [] = {17,0};
const int numerosorange = sizeof(orange) / sizeof(int); 
const int laranja [] = {4,2};
const int numeroslaranja = sizeof(laranja) / sizeof(int); 
const int verdes [] = {27,26};
const int numerosverdes = sizeof(verdes) / sizeof(int); 
const int atraso = 300;
const int botao = 15;
int estadobotao = 1;
void setup() {
 for (int i = 0; i < numeroprestage; i++){
 pinMode((prestage[i]), OUTPUT);
 }
 for (int i = 0; i < numerostage; i++){
 pinMode((stage[i]), OUTPUT);
 }
 for (int i = 0; i < numeroslaranjas; i++){
 pinMode((laranjas[i]), OUTPUT);
 }
 for (int i = 0; i < numerosorange; i++){
 pinMode((orange[i]), OUTPUT);
 }
 for (int i = 0; i < numeroslaranja; i++){
 pinMode((laranja[i]), OUTPUT);
 }
 for (int i = 0; i < numerosverdes; i++){
 pinMode((verdes[i]), OUTPUT);
 }
pinMode(botao, INPUT_PULLUP);
pinMode(25, OUTPUT);
pinMode(33, OUTPUT);
}

void loop() {
 estadobotao = digitalRead(botao);
 if (estadobotao == LOW) {
 for (int i = 0; i < numeroprestage; i++) {
  digitalWrite(prestage[i], HIGH);
  delay(atraso);
 }
 for (int i = 0; i < numerostage; i++) {
  digitalWrite(stage[i], HIGH);
  delay(atraso);
 }
 for (int i = 0; i < numeroslaranjas; i++) {
  digitalWrite(laranjas[i], HIGH);
  delay(atraso);
 }
 for (int i = 0; i < numerosorange; i++) {
  digitalWrite(orange[i], HIGH);
  delay(atraso);
 }
 for (int i = 0; i < numeroslaranja; i++) {
  digitalWrite(laranja[i], HIGH);
  delay(atraso);
 }
 for (int i = 0; i < numerosverdes; i++) {
  digitalWrite(verdes[i], HIGH);
  digitalWrite(prestage[i], LOW);
  digitalWrite(stage[i], LOW);
  digitalWrite(laranjas[i], LOW);
  digitalWrite(orange[i], LOW);
  digitalWrite(laranja[i], LOW);
  digitalWrite(verdes[i], LOW);
   }
  delay(5000);
 } else {
  digitalWrite(25, HIGH);
  digitalWrite(33, HIGH);
  digitalWrite(25, LOW);
  digitalWrite(33, LOW);
 }
 }
