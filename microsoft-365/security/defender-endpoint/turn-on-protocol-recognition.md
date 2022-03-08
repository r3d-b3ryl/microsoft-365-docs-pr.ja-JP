---
title: ユーザーのプロトコル認識を有効Microsoft Defender ウイルス対策
description: デバイスのプロトコル認識を有効Microsoft Defender ウイルス対策。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、ディフェンダー、プロトコル認識
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 02/21/2022
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: 221eff4af6bf8e77f29db84694bf3a683107fc8c
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325181"
---
# <a name="turn-on-protocol-recognition"></a>プロトコル認識を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

このポリシー設定を使用すると、既知の脆弱性の悪用に対するネットワーク保護のためのプロトコル認識を構成できます。 この設定を有効または無効にすると、プロトコル認識が有効になります。 この設定を無効にすると、プロトコル認識は無効になります。

[!IMPORTANT]
この設定は廃止されました。 

## <a name="use-group-policy-to-configure-protocol-recognition"></a>グループ ポリシーを使用してプロトコル認識を構成する

1. グループ ポリシー管理エンドポイントで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. [コンピューター構成 **] [** \> **管理用** テンプレート] Windows \> **ネットワーク** \> \> Microsoft Defender ウイルス対策 **[コンポーネント] に移動します**。

3. [プロトコル **認識] を選択します**。 既定では、この設定は有効になっています。 [構成されていません **] を設定すると**、定義の削除が有効になります。

4. ポリシーを編集するには、[ポリシー設定の **編集] リンクを選択** します。

5. [有効 **] を** 選択し、[OK] を **選択します**。

6. 更新されたグループ ポリシー オブジェクトを展開します。 「 [グループ ポリシー管理コンソール」を参照してください](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> オンプレミスでグループ ポリシー オブジェクトを使用していますか? クラウドでの翻訳方法を確認します。 [プレビュー] の [グループ ポリシー分析] を使用して、オンプレミス[のグループ ポリシー オブジェクトMicrosoft エンドポイント マネージャー分析します](/mem/intune/configuration/group-policy-analytics)。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)
- [マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
