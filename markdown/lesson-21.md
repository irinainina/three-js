# Урок 21: Импорт 3D-моделей в Three.js

## Зачем нужны модели
- Примитивы (кубы, сферы) подходят для прототипов.
- Сложные объекты (персонажи, здания, техника) лучше создавать в редакторах: **Blender**, **Maya**, **3ds Max**.

## Формат: glTF / GLB
- `.glTF` — текстовый формат + отдельные файлы
- `.glb` — бинарный, всё в одном файле (рекомендуется)

## Как загрузить модель
```bash
npm install three
```

```js
import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js';

const loader = new GLTFLoader();
loader.load('/models/model.glb', (gltf) => {
  scene.add(gltf.scene);
});
```

## Рекомендации
- Проверяй путь к модели (относительно HTML или сборщика).
- Убедись, что все текстуры включены в `.glb` (если используешь `.glTF`, они идут отдельно).
- Можно анимировать загруженные модели и обращаться к их частям через `gltf.scene.getObjectByName(...)`.

## Вывод
- Используй `GLTFLoader` для подключения моделей.
- Формат `.glb` — наиболее удобен.
- Поддерживается анимация, материалы, освещение и даже камеры.
