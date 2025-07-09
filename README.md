---

# 💰 TipJar dApp

## 📌 Español

Esta es una aplicación descentralizada (dApp) desarrollada en React + Vite que permite enviar propinas en Ethereum a través de MetaMask. La lógica del contrato inteligente está escrita en Solidity y desplegada en la red Sepolia (testnet).

---

## 🚀 Características

* Conexión con MetaMask
* Envío de propinas con mensajes personalizados
* Visualización de historial de propinas (solo para el owner del contrato)
* Visualización del balance y retiro de fondos (solo owner)
* Ranking de los mayores tippers

---

## ⚠️ IMPORTANTE e INDISPENSABLE

Antes de ejecutar esta aplicación, es **imprescindible** desplegar el contrato inteligente `TipJar.sol` en una red Ethereum compatible (como Sepolia).

### 📍 El repositorio del contrato se encuentra en:

🔗 [Repositorio GitHub](https://github.com/JoseValperga/tipjar_ethereum)

---

### 🔧 ¿Qué se necesita hacer después del deploy?

Una vez desplegado el contrato:

1. **Copiar la dirección del contrato** desde Etherscan y colocarla en el archivo `.env`:

   ```env
   VITE_CONTRACT_ADDRESS=0xTU_DIRECCION_DE_CONTRATO
   ```

2. **Copiar el ABI del contrato** desde Etherscan o desde el archivo generado por Hardhat (probablemente `ignition/deployments/chain-11155111/artifacts/TipJar#TipJar.json`) y pegarlo en:

   `src/contracts/TipJar.js`

   ```js
   export const CONTRACT_ADDRESS = import.meta.env.VITE_CONTRACT_ADDRESS;

   export const CONTRACT_ABI = [
     // 👇 Pegá aquí el contenido del campo "abi"
   ];
   ```

> ❗ Si no hacés estos pasos, la aplicación **no podrá conectarse al contrato ni funcionar correctamente**.

---

## ⚙️ Requisitos previos

* [Node.js](https://nodejs.org/) (v18 o superior)
* Navegador con [MetaMask](https://metamask.io/) instalada
* Contrato TipJar desplegado (por ejemplo, en Sepolia)
* ETH de prueba en la red correspondiente (como Sepolia)

---

## 📦 Tecnologías utilizadas

| Herramienta / Librería                                                   | Versión recomendada | Descripción                                                       |
| ------------------------------------------------------------------------ | ------------------- | ----------------------------------------------------------------- |
| [React](https://reactjs.org/)                                            | 18+                 | Librería principal para construir la interfaz de usuario          |
| [Vite](https://vitejs.dev/)                                              | 5+                  | Empaquetador rápido y ligero para aplicaciones React              |
| [ethers.js](https://docs.ethers.io/v6/)                                  | 6.x                 | Librería para interactuar con contratos en la blockchain Ethereum |
| [Tailwind CSS](https://tailwindcss.com/)                                 | 3+                  | Framework de utilidades CSS para diseño rápido y responsivo       |
| [MetaMask](https://metamask.io/)                                         | extensión navegador | Wallet que permite conectar cuentas Ethereum al navegador         |
| [dotenv (integrado en Vite)](https://vitejs.dev/guide/env-and-mode.html) | —                   | Para manejar variables de entorno como la dirección del contrato  |

> **Nota:** No se necesita instalar `dotenv` manualmente porque **Vite ya lo interpreta automáticamente** desde el archivo `.env`, siempre y cuando uses el prefijo `VITE_`.

> El archivo `.env` debe contener únicamente:

```env
VITE_CONTRACT_ADDRESS=0xTU_DIRECCION_DE_CONTRATO
```

---

## 📁 Configuración paso a paso

1. **Cloná el repositorio**:

   ```bash
   git clone https://github.com/JoseValperga/tipjar_react.git
   cd tipjar-react
   ```

2. **Instalá las dependencias**:

   ```bash
   npm install
   ```

3. **Creá el archivo `.env` en la raíz del proyecto**:

   ```bash
   touch .env
   ```

   Y agregá lo siguiente:

   ```env
   VITE_CONTRACT_ADDRESS=0xTU_DIRECCION_DE_CONTRATO
   ```

   > ⚠️ Reemplazá `0xTU_DIRECCION_DE_CONTRATO` por la dirección real del contrato desplegado en Sepolia u otra testnet compatible con MetaMask.

4. **Copiar el ABI del contrato** desde Etherscan o desde el archivo generado por Hardhat y pegarlo en:

   `src/contracts/TipJar.js`

   ```js
   export const CONTRACT_ADDRESS = import.meta.env.VITE_CONTRACT_ADDRESS;

   export const CONTRACT_ABI = [
     // 👇 Pegá aquí el contenido del campo "abi"
   ];
   ```

> ❗ Si no hacés estos pasos, la aplicación **no podrá conectarse al contrato ni funcionar correctamente**.

5. **Ejecutá el servidor de desarrollo**:

   ```bash
   npm run dev
   ```

6. **Abrí el navegador** en:

   ```
   http://localhost:5173
   ```

7. **Conectá MetaMask** y comenzá a usar la dApp ✨

---

## 📌 Importante sobre `.env`

* El archivo `.env` **no debe subirse al repositorio** (está listado en `.gitignore`).
* Solo funciona si las variables están prefijadas con `VITE_`.
* Cada vez que edites `.env`, **reiniciá el servidor** (`Ctrl + C` y luego `npm run dev`).

---

## 🧾 Licencia

MIT — José Valperga, 2025

---

## 📌 English

This is a decentralized application (dApp) built with React + Vite that allows sending Ethereum tips via MetaMask. The smart contract logic is written in Solidity and deployed on the Sepolia (testnet) network.

---

## 🚀 Features

* Connect with MetaMask
* Send tips with personalized messages
* View tip history (owner only)
* View balance and withdraw funds (owner only)
* Ranking of top tippers

---

## ⚠️ IMPORTANT AND REQUIRED

Before running this application, you **must** deploy the `TipJar.sol` smart contract to a compatible Ethereum network (like Sepolia).

### 📍 The contract repository is located at:

🔗 [GitHub Repository](https://github.com/JoseValperga/tipjar_ethereum)

---

### 🔧 What to do after deployment?

Once the contract is deployed:

1. **Copy the contract address** from Etherscan and add it to your `.env` file:

   ```env
   VITE_CONTRACT_ADDRESS=0xYOUR_CONTRACT_ADDRESS
   ```

2. **Copy the contract ABI** from Etherscan or from the Hardhat-generated file (likely `ignition/deployments/chain-11155111/artifacts/TipJar#TipJar.json`) and paste it in:

   `src/contracts/TipJar.js`

   ```js
   export const CONTRACT_ADDRESS = import.meta.env.VITE_CONTRACT_ADDRESS;

   export const CONTRACT_ABI = [
     // 👇 Paste the "abi" field content here
   ];
   ```

> ❗ Without these steps, the app **won’t be able to connect to the contract or work properly**.

---

## ⚙️ Prerequisites

* [Node.js](https://nodejs.org/) (v18 or higher)
* Browser with [MetaMask](https://metamask.io/) installed
* Deployed TipJar contract (for example, on Sepolia)
* Test ETH on the corresponding network (like Sepolia)

---

## 📦 Technologies Used

| Tool / Library                                                         | Recommended Version | Description                                                 |
| ---------------------------------------------------------------------- | ------------------- | ----------------------------------------------------------- |
| [React](https://reactjs.org/)                                          | 18+                 | Main library for building the UI                            |
| [Vite](https://vitejs.dev/)                                            | 5+                  | Fast, lightweight bundler for React applications            |
| [ethers.js](https://docs.ethers.io/v6/)                                | 6.x                 | Library to interact with Ethereum smart contracts           |
| [Tailwind CSS](https://tailwindcss.com/)                               | 3+                  | Utility-first CSS framework for rapid and responsive design |
| [MetaMask](https://metamask.io/)                                       | Browser extension   | Wallet that connects Ethereum accounts to the browser       |
| [dotenv (built into Vite)](https://vitejs.dev/guide/env-and-mode.html) | —                   | To handle environment variables like the contract address   |

> **Note:** You don’t need to install `dotenv` manually because **Vite automatically loads `.env` files** as long as you use the `VITE_` prefix.

> The `.env` file should contain only:

```env
VITE_CONTRACT_ADDRESS=0xYOUR_CONTRACT_ADDRESS
```

---

## 📁 Step-by-step setup

1. **Clone the repository**:

   ```bash
   git clone https://github.com/JoseValperga/tipjar_react.git
   cd tipjar-react
   ```

2. **Install dependencies**:

   ```bash
   npm install
   ```

3. **Create the `.env` file in the project root**:

   ```bash
   touch .env
   ```

   Add the following:

   ```env
   VITE_CONTRACT_ADDRESS=0xYOUR_CONTRACT_ADDRESS
   ```

   > ⚠️ Replace `0xYOUR_CONTRACT_ADDRESS` with your actual deployed contract address on Sepolia or another MetaMask-compatible testnet.

4. **Copy the contract ABI** from Etherscan or from the Hardhat-generated file and paste it in:

   `src/contracts/TipJar.js`

   ```js
   export const CONTRACT_ADDRESS = import.meta.env.VITE_CONTRACT_ADDRESS;

   export const CONTRACT_ABI = [
     // 👇 Paste the "abi" field content here
   ];
   ```

> ❗ Without these steps, the app **won’t be able to connect to the contract or work properly**.

5. **Run the development server**:

   ```bash
   npm run dev
   ```

6. **Open the browser** at:

   ```
   http://localhost:5173
   ```

7. **Connect MetaMask** and start using the dApp ✨

---

## 📌 About `.env`

* The `.env` file **must not be committed** (it’s in `.gitignore`).
* Variables only work with the `VITE_` prefix.
* Every time you edit `.env`, **restart the server** (`Ctrl + C` then `npm run dev`).

---

## 🧾 License

MIT — José Valperga, 2025

---
