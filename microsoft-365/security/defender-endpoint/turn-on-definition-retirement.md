---
title: Microsoft Defender ウイルス対策の定義の廃止を有効にする
description: Microsoft Defender ウイルス対策の定義の廃止を有効にします。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、Defender、定義の廃止
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: dd9cd313dec962547acef85c6da326d3b6e5c58f
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167636"
---
# <a name="turn-on-definition-retirement"></a>定義の廃止を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

グループ ポリシーを使用して定義の廃止を構成できます。 定義の廃止により、コンピューターに特定の脆弱性から保護するために必要なセキュリティ更新プログラムがあるかどうかを確認します。 システムが定義によって検出された悪用に対して脆弱でない場合、その定義は "廃止" されます。 特定のプロトコルのすべてのセキュリティ インテリジェンスが廃止された場合、そのプロトコルは解析されなくなります。 この機能を有効にすると、パフォーマンスが向上します。 最新のセキュリティ更新プログラムがすべて最新のコンピューターでは、ネットワーク保護はネットワークパフォーマンスに影響しません。

## <a name="use-group-policy-to-configure-definition-retirement"></a>グループ ポリシーを使用して定義の廃止を構成する

1. グループ ポリシー管理エンドポイントで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. **ネットワーク検査システム** Microsoft Defender ウイルス対策 **コンポーネント** \>  \> Windows **コンピューター構成** \> **管理テンプレート**\>に移動します。

3. [ **定義の廃止を有効にする]** を選択します。 既定では、この設定は有効になっています。 **[未構成]** に設定すると、定義の廃止が有効になります。

4. ポリシーを編集するには、ポリシー **設定の編集** リンクを選択します。

5. **[有効] を** 選択し、[OK] を選択 **します**。

6. 更新した グループ ポリシー オブジェクトをデプロイします。 [管理コンソールグループ ポリシー参照してください](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> グループ ポリシー オブジェクトをオンプレミスで使用していますか? クラウドで翻訳する方法を確認します。 [Microsoft エンドポイント マネージャー - プレビューのグループ ポリシー分析を使用して、オンプレミス のグループ ポリシー オブジェクトを分析](/mem/intune/configuration/group-policy-analytics)します。
