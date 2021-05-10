---
title: ユーザーの定義の削除を有効Microsoft Defender ウイルス対策
description: ユーザーの定義の削除を有効Microsoft Defender ウイルス対策。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、ディフェンダー、定義の削除
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296480"
---
# <a name="turn-on-definition-retirement"></a>定義の削除を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

グループ ポリシーを使用して定義の削除を構成できます。 定義の削除は、特定の脆弱性からコンピューターを保護するために必要なセキュリティ更新プログラムがコンピューターに存在する場合にチェックします。 システムが定義によって検出された悪用に対して脆弱ではない場合、その定義は "廃止" されます。 特定のプロトコルのすべてのセキュリティ インテリジェンスが廃止された場合、そのプロトコルは解析されなくなりました。 この機能を有効にすると、パフォーマンスが向上します。 最新のセキュリティ更新プログラムが適用されているコンピューターでは、ネットワーク保護はネットワークのパフォーマンスに影響を与えかねない。

## <a name="use-group-policy-to-configure-definition-retirement"></a>グループ ポリシーを使用して定義の削除を構成する

1. グループ ポリシー管理エンドポイントで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. [コンピューターの **構成]**  >  **[管理用**  >  **テンプレート] Windowsネットワーク**  >  **Microsoft Defender ウイルス対策**  >  **システム] に移動します**。 

3. [定義 **の削除を有効にする] を選択します**。 既定では、この設定は有効になっています。 [構成されていません **] を設定すると**、定義の削除が有効になります。 

4. ポリシーを編集するには、[ポリシー設定の **編集] リンクを選択** します。

5. [有効 **] を** 選択し **、[OK] を選択します**。

6. 更新されたグループ ポリシー オブジェクトを展開します。 「 [グループ ポリシー管理コンソール」を参照してください](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> オンプレミスでグループ ポリシー オブジェクトを使用していますか? クラウドでの翻訳方法を確認します。 [[プレビュー] でグループ ポリシー分析を使用して、オンプレミスのグループ ポリシー Microsoft エンドポイント マネージャーを分析します](/mem/intune/configuration/group-policy-analytics)。 
  
## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
 
- [クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)

- [マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)