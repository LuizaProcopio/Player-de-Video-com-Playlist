
# 🎬 Player de Vídeo com Playlist (TypeScript)

Este projeto implementa um **player de vídeo com suporte a playlists** utilizando **TypeScript** e conceitos fundamentais de **Programação Orientada a Objetos (POO)**, como **abstração, encapsulamento, herança e polimorfismo**.

---

## ✅ **Como executar o projeto**

### **1. Clonar o repositório**
```bash
git clone <URL_DO_REPOSITORIO>
cd Player-de-Video-com-Playlist
```

### **2. Instalar dependências**
```bash
npm install
```

### **3. Estrutura do projeto**
```
PLAYER-DE-VIDEO-COM-PLAYLIST
│
├── classes
│   ├── Advideo.ts
│   ├── LiveStream.ts
│   ├── Player.ts
│   ├── Playlist.ts
│   └── Video.ts
│
├── interfaces
│   ├── IPlayable.ts
│   └── IPlayerControls.ts
│
└── main.ts
```

- **`classes/`** → Contém as classes principais do projeto.
- **`interfaces/`** → Define contratos para garantir consistência no código.
- **`main.ts`** → Ponto de entrada do programa.

---

### **4. Executar em modo desenvolvimento**
Utilize o `ts-node` via **npx**:

```bash
npx ts-node main.ts
```

---

### **5. Compilar para JavaScript**
```bash
npm run build
```

---

### **6. Executar versão compilada**
```bash
npm run serve
```

---

## 📌 **Descrição do Projeto**
O sistema simula um **Player de Vídeo com suporte a playlists** e anúncios, seguindo a lógica de um player real.  
Ele oferece funcionalidades como:
- Adicionar vídeos a uma playlist.
- Reproduzir vídeos normais, anúncios (Ads) e transmissões ao vivo.
- Controles de play, pause e skip.
- Uso de **interfaces** para definir comportamentos obrigatórios.

---

## 🧩 **Onde os pilares da POO foram aplicados**

### ✅ **1. Abstração**
- Interfaces **`IPlayable`** e **`IPlayerControls`** foram criadas para definir **comportamentos obrigatórios** que qualquer classe deve implementar.
- Exemplo:
```typescript
interface IPlayable {
  play(): void;
  pause(): void;
}
```

---

### ✅ **2. Encapsulamento**
- Propriedades das classes como **`title`, `duration` e `isPlaying`** estão encapsuladas usando `private` ou `protected`.
- Métodos públicos controlam como essas propriedades são acessadas e modificadas.
- Exemplo:
```typescript
class Video {
  private title: string;
  constructor(title: string) {
    this.title = title;
  }
}
```

---

### ✅ **3. Herança**
- A classe **`AdVideo`** e **`LiveStream`** herdam da classe base **`Video`**.
- Exemplo:
```typescript
class AdVideo extends Video {
  constructor(title: string, duration: number) {
    super(title, duration);
  }
}
```

---

### ✅ **4. Polimorfismo**
- O método **`play()`** é sobrescrito em diferentes classes (`Video`, `AdVideo`, `LiveStream`) para ter comportamentos distintos.
- Exemplo:
```typescript
class LiveStream extends Video {
  play(): void {
    console.log(`Transmitindo ao vivo: ${this.title}`);
  }
}
```

---

## 🏗 **Principais Classes e Interfaces**

- **`Video.ts`** → Classe base para qualquer tipo de vídeo.
- **`AdVideo.ts`** → Representa anúncios, herdando de `Video`.
- **`LiveStream.ts`** → Representa transmissões ao vivo, herdando de `Video`.
- **`Player.ts`** → Gerencia a reprodução dos vídeos.
- **`Playlist.ts`** → Armazena e gerencia uma lista de vídeos.
- **`IPlayable.ts`** → Interface para objetos que podem ser reproduzidos.
- **`IPlayerControls.ts`** → Interface para controles do player.

---

## ▶ **Exemplo de execução**
Quando rodar `main.ts`, você verá algo como:

```
Adicionando vídeos à playlist...
Reproduzindo: Video 1
Pausando: Video 1
Reproduzindo: Anúncio 1
Transmitindo ao vivo: Live 1
```
