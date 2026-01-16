## ImageSliderComponent

Responsive, loop destekli, autoplay özellikli ve **zoom (pinch-to-zoom)** destekleyen bir React Native image slider bileşenidir.

Bu component **React Native** projeleri için geliştirilmiştir ve zoom / gesture işlemleri için
**react-native-gesture-handler** kullanır.

---

## 📦 Gerekli Paketler

Bu component’in çalışabilmesi için aşağıdaki paket **zorunludur**:

```bash
npm install react-native-gesture-handler



### Kullanım Örneği

```typescript
import React from 'react';
import { SafeAreaView } from 'react-native';
import ImageSliderComponent from '@yrncskn/imageslider';

const images = [
  { id: 1, images: 'https://picsum.photos/id/10/800/400' },
  { id: 2, images: 'https://picsum.photos/id/20/800/400' },
];

export default function App() {
  return (
    <SafeAreaView style={{ flex: 1 }}>
      <ImageSliderComponent
        images={images}
        autoPlay={true}
        isActiveZooming={true}
        dotpagination={true}
        aspectRatio="16 / 9"
      />
    </SafeAreaView>
  );
}


```


```typescript
interface FileInfo {
  image:ImageItem[]     // Zorunlu	Görüntülenecek görsel listesi. {id, image} yapısında olmalıdır.
  mainSlideWidth: number;     // lider bileşeninin toplam genişliği.
  autoPlay: boolean;     // Görsellerin otomatik olarak kaydırılıp kaydırılmayacağı.
  dotpagination: boolean;      // Alt kısımda noktalarla sayfalama göstergesini açar.
  numberpagination: boolean ; // Alt kısımda numaralarla sayfalama göstergesini açar.
    
    haveArrows: boolean ;    // Sağ ve sol yön oklarını aktif eder.
  showIndexCounter: boolean;     // Sağ alt köşede 1 / 5 gibi bir sayaç gösterir.
  aspectRatio: string;     // Görselin en-boy oranı. Örn: "1/1", "16/9".
  isActiveZooming: boolean;      //  Slider üzerine tıklandığında Pinch-to-Zoom destekli modalı açar.
  onImagePress: (item: Item) => void; // undefined	Görsele tıklandığında çalışacak fonksiyon (Zoom'dan önceliklidir).

   
}
```