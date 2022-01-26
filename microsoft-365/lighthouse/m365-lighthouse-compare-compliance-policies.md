---
title: デバイス コンプライアンス ポリシーの設定を比較する
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
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseコンプライアンス ポリシー設定を比較する方法について説明します。
ms.openlocfilehash: 05f67cda1e99aff0b43109c5f55f78efaf30049c
ms.sourcegitcommit: f3c912780bbcf5a5b47de192202adb3afbd5952b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2022
ms.locfileid: "62219027"
---
# <a name="compare-device-compliance-policy-settings"></a>デバイス コンプライアンス ポリシーの設定を比較する

> [!NOTE]
> この記事で説明する機能はプレビュー段階であり、変更される可能性があり、[要件](m365-lighthouse-requirements.md)を満たすパートナーのみが利用できます。 組織に Microsoft 365 Lighthouse がない場合は、「[Microsoft 365 Lighthouse にサインアップする](m365-lighthouse-sign-up.md)」を参照してください。

Microsoft 365 Lighthouseを使用すると、テナント全体のコンプライアンス ポリシーを 1 つのビューで表示できます。 ポリシーを比較することで、テナント全体のセキュリティと標準化を推進できます。 ビューをフィルター処理して、構成済みの設定 (構成されていない設定と比較)、構成が異なる設定、または一致する設定を表示できます。 また、関心のある特定の設定を検索し、ポリシー間の比較方法を確認することもできます。

## <a name="before-you-begin"></a>はじめに

- デバイスは Intune ライセンスを持ち、デバイス (MEM) に登録Microsoft エンドポイント マネージャー必要があります。

## <a name="compare-policy-settings"></a>ポリシー設定の比較

1. ライトハウスの左側のナビゲーション ウィンドウで、[デバイス] を **選択します**。

2. **[ポリシー]** タブを選択します。

3. [フィルター **] ドロップダウン** リストから、オペレーティング システム/プラットフォームを選択します。

   > [!NOTE]
   > ポリシーを比較できるのは、同じオペレーティング システム/プラットフォームのみです。

4. フィルター処理された一覧から、比較するポリシーを最大 3 つ選択します。

5. [比較 **] を選択します**。

結果をフィルター処理して **、異なる** 設定一致する設定、または構成済みの **設定を****確認できます**。

## <a name="configure-a-policy-setting"></a>ポリシー設定の構成

1. ライトハウスの左側のナビゲーション ウィンドウで、[デバイス] を **選択します**。

2. **[ポリシー]** タブを選択します。

3. 一覧からポリシー名を選択します。

4. [ポリシーの詳細] ウィンドウで、[このポリシー **を表示する**] を選択Microsoft エンドポイント マネージャー。

5. MEM で、必要に応じてポリシー設定を編集します。

## <a name="next-steps"></a>次の手順

ポリシーの調整を行う際は、現在の基準計画設定に対して変更を評価してください。 詳細については、「基準計画を [使用した標準テナント構成の展開の概要」を参照してください](m365-lighthouse-deploy-standard-tenant-configurations-overview.md)。

## <a name="related-content"></a>関連コンテンツ

[Intune へのデバイスの登録とは](/mem/intune/enrollment/device-enrollment) (記事)  
[コンプライアンス ポリシーを使用して Intune で管理](/mem/intune/protect/device-compliance-get-started) するデバイスのルールを設定する (記事)  
[基準計画を使用した標準テナント構成の展開の概要](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (記事)
