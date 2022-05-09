---
title: Microsoft 365 Lighthouseのデバイス コンプライアンス ポリシー設定を比較する
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、デバイス コンプライアンス ポリシーの設定を比較する方法について説明します。
ms.openlocfilehash: 1ea7a278a58cd6d864c32ab7b25569ae463658f9
ms.sourcegitcommit: 339d2c2ffea06726f69429f73c1113c649f37b18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65022772"
---
# <a name="compare-device-compliance-policy-settings-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseのデバイス コンプライアンス ポリシー設定を比較する

Microsoft 365 Lighthouseでは、テナント全体のコンプライアンス ポリシーを 1 つのビューで表示できます。 ポリシーを比較することで、テナント全体のセキュリティと標準化を推進できます。 ビューをフィルター処理して、構成されている設定 (未構成の設定と構成されていない設定) 、構成が異なる設定、または一致する設定を表示できます。 また、特定の設定を検索して、ポリシー間での比較方法を確認することもできます。

## <a name="before-you-begin"></a>開始する前に

デバイスにMicrosoft Intune ライセンスがあり、Microsoft エンドポイント マネージャー (MEM) に登録されていることを確認します。

## <a name="compare-policy-settings"></a>ポリシー設定を比較する

1. Lighthouse の左側のナビゲーション ウィンドウで、[デバイス] を選択 **します**。

2. **[ポリシー]** タブを選択します。

3. **[フィルター**] ドロップダウン リストから、オペレーティング システムまたはプラットフォームを選択します。

   > [!NOTE]
   > ポリシーを比較できるのは、同じオペレーティング システムまたはプラットフォームのみです。

4. フィルター処理された一覧から、比較するポリシーを最大 3 つ選択します。

5. **[比較**] を選択します。

結果をフィルター処理して **、異なる設定**、**一致する設定**、または **構成済みの設定** を表示できます。

## <a name="configure-a-policy-setting"></a>ポリシー設定を構成する

1. Lighthouse の左側のナビゲーション ウィンドウで、[デバイス] を選択 **します**。

2. **[ポリシー]** タブを選択します。

3. 一覧からポリシー名を選択します。

4. [ポリシーの詳細] ウィンドウ **で、[Microsoft エンドポイント マネージャーでこのポリシーを表示する**] を選択します。

5. MEM で、必要に応じてポリシー設定を編集します。

## <a name="next-steps"></a>次の手順

ポリシーの調整を行う際は、現在のベースライン設定に対して変更を評価してください。 詳細については、 [ベースラインを使用して標準テナント構成をデプロイする方法の概要に関するページを](m365-lighthouse-deploy-standard-tenant-configurations-overview.md)参照してください。

## <a name="related-content"></a>関連コンテンツ

[Intune へのデバイスの登録とは](/mem/intune/enrollment/device-enrollment) (記事)  
[コンプライアンス ポリシーを使用して、Intuneで管理するデバイスのルールを設定する](/mem/intune/protect/device-compliance-get-started) (記事)  
[Microsoft 365 Lighthouseベースラインを使用して標準テナント構成をデプロイする方法の概要](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (記事)
