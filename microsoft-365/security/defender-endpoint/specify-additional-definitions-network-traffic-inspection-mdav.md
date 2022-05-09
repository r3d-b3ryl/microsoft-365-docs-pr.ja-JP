---
title: Microsoft Defender ウイルス対策のネットワーク トラフィック検査に追加の定義セットを指定する
description: Microsoft Defender ウイルス対策のネットワーク トラフィック検査に追加の定義セットを指定します。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、ネットワーク トラフィック検査
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: f7b940604272035dc37b170eb759fa0ec45582b6
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165872"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>ネットワーク トラフィック検査用に追加の定義セットを指定する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

グループ ポリシーを使用して、ネットワーク トラフィック検査用に追加の定義セットを指定できます。

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>グループ ポリシーを使用して、ネットワーク トラフィック検査用の追加の定義セットを指定する

1. グループ ポリシー管理エンドポイントで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

2. **ネットワーク検査システム** Microsoft Defender ウイルス対策 **Windows** \> **コンポーネント**\>に移動します。

3. **[ネットワーク トラフィック検査に追加の定義セットを指定** する] を選択します。 既定では、このポリシーは **[未構成]** に設定されています。

4. ポリシーを編集するには、ポリシー **設定の編集** リンクを選択します。

5. **[有効] を** 選択し、[**オプション]** セクションで [**表示...**] を選択します。

6. 一覧にエントリを追加し、[OK] を選択 **します**。

   各エントリは名前と値のペアとして一覧表示する必要があります。名前は定義セット GUID の文字列形式です。 たとえば、テスト セキュリティ インテリジェンスを有効にする定義セット GUID は次のように定義されています `{b54b6ac9-a737-498e-9120-6616ad3bf590}`。 この値は使用されないため、値を `0`.

7. **[OK] を** 選択し、更新された グループ ポリシー オブジェクトをデプロイします。 [管理コンソールグループ ポリシー参照してください](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> グループ ポリシー オブジェクトをオンプレミスで使用していますか? クラウドで翻訳する方法を確認します。 [Microsoft エンドポイント マネージャー - プレビューのグループ ポリシー分析を使用して、オンプレミス のグループ ポリシー オブジェクトを分析](/mem/intune/configuration/group-policy-analytics)します。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)
- [マルウェア対策ポリシーを作成してデプロイする方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)