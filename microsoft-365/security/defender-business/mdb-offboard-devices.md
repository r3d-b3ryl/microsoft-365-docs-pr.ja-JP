---
title: Microsoft Defender for Businessからデバイスをオフボードにする
description: Microsoft Defender for Businessからデバイスを削除またはオフボードする方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 24c6e511b32b88ca72de7a7a0654fbea2761bf78
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67325641"
---
# <a name="offboard-a-device-from-microsoft-defender-for-business"></a>Microsoft Defender for Businessからデバイスをオフボードにする

デバイスをオフボードにする場合は、次のいずれかの手順を使用します:

- [Windows デバイスをオフボードにする](#offboard-a-windows-device)
- [Mac をオフボードにする](#offboard-a-mac)

## <a name="offboard-a-windows-device"></a>Windows デバイスをオフボードにする

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、[**設定**] を選択し、[**エンドポイント**] を選択します。

3. [**デバイス管理**] で、[**オフボード**] を選択します。

4. **Windows 10 や 11** などのオペレーティング システムを選択し、[**デバイスのオフボード**] の [**展開方法**] セクションで [**ローカル スクリプト**] を選択します。 

5. 確認画面で情報を確認し、[**ダウンロード**] を選択して続行します。

6. [**オフボード パッケージのダウンロード**] を選択します。オフボード パッケージをリムーバブル ドライブに保存することをお勧めします。

7. オフボードする各デバイスでスクリプトを実行します。

## <a name="offboard-a-mac"></a>Mac をオフボードにする

1. **Finder** >  アプリケーションに移動 **します**。 

2. **Microsoft Defender for Business** を右クリックし、[**ごみ箱に移動**] を選択します。 <br/>--- または --- <br/> 次のコマンドを使用します `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`。

> [!IMPORTANT]
> デバイスをオフボードすると、デバイスは Defender for Business へのデータの送信を停止します。 ただし、オフボードの前に受信したデータは、最大 6 か月間保持されます。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for BusinessでMicrosoft Defender 脆弱性の管理 ダッシュボードを使用する](mdb-view-tvm-dashboard.md)
- [Microsoft Defender for Businessでポリシーを表示または編集する](mdb-view-edit-create-policies.md)
- [Microsoft Defender for Businessでデバイスを管理する](mdb-manage-devices.md)