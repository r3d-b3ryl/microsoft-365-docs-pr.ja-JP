---
title: Microsoft Defender ウイルス対策のプロトコル認識を有効にする
description: Microsoft Defender ウイルス対策のプロトコル認識を有効にします。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、Defender、プロトコル認識
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

このポリシー設定を使用すると、既知の脆弱性の悪用に対するネットワーク保護のプロトコル認識を構成できます。 この設定を有効または未構成にすると、プロトコル認識が有効になります。 この設定を無効にすると、プロトコル認識は無効になります。

[!IMPORTANT]
この設定は非推奨になりました。 

## <a name="use-group-policy-to-configure-protocol-recognition"></a>グループ ポリシーを使用してプロトコル認識を構成する

1. グループ ポリシー管理エンドポイントで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. **ネットワーク検査システム** Microsoft Defender ウイルス対策 **コンポーネント** \>  \> Windows **コンピューター構成** \> **管理テンプレート**\>に移動します。

3. **プロトコル認識を選択します**。 既定では、この設定は有効になっています。 **[未構成]** に設定すると、定義の廃止が有効になります。

4. ポリシーを編集するには、ポリシー **設定の編集** リンクを選択します。

5. **[有効] を** 選択し、[OK] を選択 **します**。

6. 更新した グループ ポリシー オブジェクトをデプロイします。 [管理コンソールグループ ポリシー参照してください](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> グループ ポリシー オブジェクトをオンプレミスで使用していますか? クラウドで翻訳する方法を確認します。 [Microsoft エンドポイント マネージャー - プレビューのグループ ポリシー分析を使用して、オンプレミス のグループ ポリシー オブジェクトを分析](/mem/intune/configuration/group-policy-analytics)します。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)
- [マルウェア対策ポリシーを作成してデプロイする方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
