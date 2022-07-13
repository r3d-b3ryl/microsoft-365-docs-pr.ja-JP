---
title: Microsoft Defender for Business サーバーを取得する
description: 現在プレビュー段階のMicrosoft Defender for Business サーバーを取得する方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: none
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security-compliance
ms.openlocfilehash: c11a32ac4658750e3c5265ae42a91ad076efecd1
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773299"
---
# <a name="how-to-get-microsoft-defender-for-business-servers-preview"></a>Microsoft Defender for Business サーバーを取得する方法 (プレビュー)

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。 

2. プレビュー設定をオンにします。 

   1. ナビゲーション ウィンドウで、[**設定** \> **エンドポイント** \> **の高度な機能**] **プレビュー機能**\>を選択します。 
   2. 設定を **[オン]** にし、[ **保存] を** 選択します。

3. Windows Server の適用スコープを有効にします。 

   1. **[設定**\>エンドポイント **の構成管理** \> **の適用] スコープ** に移動 **します**\>。 
   2. [ **MDE を使用して MEM からセキュリティ構成設定を適用する**] を選択し、  **Windows Server** を選択して、[保存] を選択 **します**。

4. オンボード デバイスの Windows Server と Linux Server のガイダンスに従って[、Microsoft Defender for Businessに](mdb-onboard-devices.md)進みます。

> [!IMPORTANT]
> Microsoft Defender for Business サーバーは現在プレビュー段階です。 一般公開 (GA) になると、Microsoft 365 Business Premiumと Defender for Business のスタンドアロン バージョンのアドオンとして提供されます。 GA では、Microsoft Defender for Business サーバーの料金は、サーバー インスタンスあたり 3 ドルです。

## <a name="see-also"></a>関連項目

- [試用版プレイブック:Microsoft Defender for Businessを参照してください](trial-playbook-defender-business.md)。
- [Microsoft Defender for Businessでセットアップ ウィザードを使用します](mdb-use-wizard.md)。
- [Defender for Business のセットアップと構成プロセスを参照してください](mdb-setup-configuration.md)。
- [Defender for Business のヘルプとサポートを受ける方法について説明](mdb-get-help.md) します (サポートが必要な場合に備えて)。