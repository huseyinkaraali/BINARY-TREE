İFADE AĞAÇLARI

İşleçlerin iç düğümlerde saklandığı ve işlenenlerin yapraklarda sıralandığı ikili bir ağaçtır.

.Bir ifadeyi değerlendirmek için kullanılır .

Bir ifadeyi değerlendirmek için kullanılır.

Bir infix ifadesini prefix veya postfix gösterimine dönüştürmek için kullanılır.

Ağaç yapısı, operatörlerin değerlendirilme sırasına dayanır. Önce alt düzey düğümlerdeki operatörler değerlendirlir.
Değerlendirilen son operatör kök düğümdedir.

![image](https://user-images.githubusercontent.com/123556095/230583296-0fc58570-bc70-4fb2-b2e3-1fc3f93b3858.png)

İFADE AĞACI DEĞERLENDİRMESİ
- İfadeyi değerlendirmek için bir algoritma geliştirebiliriz.
Her alt ağaç geçerli bir alt ifadeyi temsil eder.
Daha düşük seviyeli alt ağaçlar daha yüksek önceliğe sahiptir 
Her düğüm için önce iki alt ağaç değerlendirilmelidir. 

Nasıl çalışır ?     

![image](https://user-images.githubusercontent.com/123556095/230584736-25166480-fa5f-4c9e-b5e0-04667aa0a176.png)

DİZE GÖSTERİMİ 

. Gerekli parantezler eksik olduğu için sonuç doğru değildi.
. Tam parantezli bir ifadeyi kolayca oluşturabilir. 

Bu _str_() yöntemini uygulamak için sınıf etkinliği.

![image](https://user-images.githubusercontent.com/123556095/230585319-3169bc59-9ce8-4135-b76e-63481e7f4028.png)

![image](https://user-images.githubusercontent.com/123556095/230592062-b8901e2e-d577-4b27-a774-dd66fbe58f75.png)



KOD ALANI

#include <stdio.h>
#include <stdlib.h>

// Ağaç düğümünün tanımı
struct node {
    int data;
    struct node* left;
    struct node* right;
};

// Yeni bir düğüm oluşturur
struct node* newNode(int data) {
    struct node* node = (struct node*) malloc(sizeof(struct node));
    node->data = data;
    node->left = NULL;
    node->right = NULL;
    return(node);
}

// Ağaçtaki düğümlerin alt düğümlerinin toplamını hesaplar
int sumOfChildren(struct node* node) {
    if (node == NULL) {
        return 0;
    }
    int sum = 0;
    if (node->left != NULL) {
        sum += node->left->data;
    }
    if (node->right != NULL) {
        sum += node->right->data;
    }
    return sum;
}

int main() {
    // 3 düğümlük ikili ağacı oluştur
    struct node* root = newNode(1);
    root->left = newNode(2);
    root->right = newNode(3);

    // Gövdenin alt düğümlerinin toplamını hesapla
    int sum = sumOfChildren(root);

    // Sonucu ekrana yazdır
    printf("Gövdenin alt düğümlerinin toplamı: %d\n", sum);

    return 0;
}






