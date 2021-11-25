---
title: ユーザーのプロトコル認識を有効Microsoft Defender ウイルス対策
description: デバイスのプロトコル認識を有効Microsoft Defender ウイルス対策。
keywords: Microsoft Defender ウイルス対策マルウェア対策、セキュリティ、防御側、プロトコル認識
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
ms.collection: m365-security-compliance
ms.openlocfilehash: cbb9b50714d252d86fcbaed9b43684351f903251
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167624"
---
# <a name="turn-on-protocol-recognition"></a>プロトコル認識を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

このポリシー設定を使用すると、既知の脆弱性の悪用に対するネットワーク保護のためのプロトコル認識を構成できます。 この設定を有効または無効にすると、プロトコル認識が有効になります。 この設定を無効にすると、プロトコル認識は無効になります。

## <a name="use-group-policy-to-configure-protocol-recognition"></a>グループ ポリシーを使用してプロトコル認識を構成する

1. グループ ポリシー管理エンドポイントで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. [コンピューターの **構成]** \> **[管理用** \> **テンプレート] Windowsネットワーク** \> **Microsoft Defender ウイルス対策** \> **システム] に移動します**。

3. プロトコル **認識を選択します**。 既定では、この設定は有効になっています。 [構成されていません **] を設定すると**、定義の削除が有効になります。

4. ポリシーを編集するには、[ポリシー設定の **編集] リンクを選択** します。

5. [有効 **] を** 選択し **、[OK] を選択します**。

6. 更新されたグループ ポリシー オブジェクトを展開します。 「 [グループ ポリシー管理コンソール」を参照してください](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> オンプレミスでグループ ポリシー オブジェクトを使用していますか? クラウドでの翻訳方法を確認します。 [[プレビュー] でグループ ポリシー分析を使用して、オンプレミスのグループ ポリシー Microsoft エンドポイント マネージャーを分析します](/mem/intune/configuration/group-policy-analytics)。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)
- [マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)