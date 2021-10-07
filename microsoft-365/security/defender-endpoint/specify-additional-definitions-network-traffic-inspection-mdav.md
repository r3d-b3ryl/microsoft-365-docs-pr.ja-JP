---
title: ネットワーク トラフィック検査用の追加の定義セットを指定Microsoft Defender ウイルス対策
description: ネットワーク トラフィック検査用の追加の定義セットを指定Microsoft Defender ウイルス対策。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御者、ネットワーク トラフィック検査
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
ms.openlocfilehash: a9deaa216de6cc8c744c6f8eca94dbf8868be0d6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166256"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>ネットワーク トラフィック検査用の追加の定義セットを指定する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

グループ ポリシーを使用して、ネットワーク トラフィック検査の追加の定義セットを指定できます。

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>グループ ポリシーを使用して、ネットワーク トラフィック検査用の追加の定義セットを指定する

1. グループ ポリシー管理エンドポイントで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. [ネットワーク検査 **システムWindowsコンポーネントMicrosoft Defender ウイルス対策** \>  \> **に移動します**。

3. [ネットワーク **トラフィック検査の追加の定義セットを指定する] を選択します**。 既定では、このポリシーは [構成されていません] **に設定されています**。

4. ポリシーを編集するには、[ポリシー設定の **編集] リンクを選択** します。

5. [ **有効] を** 選択し、[オプション] **セクションで** [ **表示...] を選択します**。

6. リストにエントリを追加し **、[OK] を選択します**。

   各エントリは、名前と値のペアとして一覧表示する必要があります。名前は、定義セット GUID の文字列表現です。 たとえば、テスト セキュリティ インテリジェンスを有効にする定義セット GUID は、次のように定義されます `{b54b6ac9-a737-498e-9120-6616ad3bf590}` 。 値は使用されないので、に設定することをお勧めします `0` 。

7. **[OK] を** 選択し、更新されたグループ ポリシー オブジェクトを展開します。 「 [グループ ポリシー管理コンソール」を参照してください](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> オンプレミスでグループ ポリシー オブジェクトを使用していますか? クラウドでの翻訳方法を確認します。 [[プレビュー] でグループ ポリシー分析を使用して、オンプレミスのグループ ポリシー Microsoft エンドポイント マネージャーを分析します](/mem/intune/configuration/group-policy-analytics)。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)
- [マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)