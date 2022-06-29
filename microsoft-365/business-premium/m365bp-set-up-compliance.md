---
title: コンプライアンス機能をセットアップする
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: データ損失を防ぎ、お客様と顧客の機密情報を安全に保つためのコンプライアンス機能を設定します。
ms.openlocfilehash: ad95e4dc99a9957812ee09ace69d66b169ef7879
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66491899"
---
# <a name="set-up-compliance-features"></a>コンプライアンス機能をセットアップする

Microsoft 365 Business Premium サブスクリプションには、コンプライアンス機能とプライバシー機能が含まれています。 これらの機能は、会社のデータを保護し、ユーザーと顧客の機密情報をセキュリティで保護するのに役立ちます。 この記事は、コンプライアンス機能の使用を開始するために設計されています。

## <a name="before-you-begin"></a>開始する前に

Azure Active Directoryで、次のいずれかの役割が割り当てられていることを確認します。

- グローバル管理者
- コンプライアンス管理者

詳細については、「[役割ページの使用を開始する](../admin/add-users/admin-roles-page.md)」を参照してください。

## <a name="use-compliance-manager-to-get-started"></a>コンプライアンス マネージャーを使用して作業を開始する

:::image type="content" source="./media/m365bp-compliancemanager.png" alt-text="Microsoft 365 Business Premium のコンプライアンス マネージャーのスクリーンショット。":::

Microsoft 365 Business Premium には、コンプライアンス機能の設定を開始するのに役立つコンプライアンス マネージャーが含まれています。 機能には、データ損失防止、データ ライフサイクル管理、インサイダー リスク管理などが含まれます。 コンプライアンス マネージャーは、推奨事項、コンプライアンス スコア、およびスコアを向上させる方法を強調することで、時間を節約できます。

作業を開始する方法を次に示します。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com) に移動し、サインインします。

2. ナビゲーション ウィンドウで、**[コンプライアンス マネージャー]** を選択します。

3. **[概要]** タブで、情報を確認します。 アイテムまたはリンクを選択して詳細情報を表示したり、データ損失防止 (DLP) ポリシーの構成などのアクションを実行したりできます。 たとえば、**[スコアに影響を与えるソリューション]** セクションで、**[残りのアクション]** 列のリンクを選択できます。

   :::image type="content" source="./media/m365bp-compliancesolutions.png" alt-text="[スコア] ウィンドウに影響を与えるソリューションのスクリーンショット。":::

   このアクションを実行すると、**[改善アクション]** タブが表示され、選択したアイテムに対してフィルター処理されます。 この例では、構成する DLP ポリシーを確認しています。

   :::image type="content" source="./media/m365bp-dlppoliciestoconfigure.png" alt-text="構成する DLP ポリシーのスクリーンショット。":::

4. **[改善アクション]** タブで、アイテムを選択します。 この例では、**[カスタマイズされた DLP ポリシーまたは個人を特定できる情報の作成]** を選択しました。 構成するポリシーに関する詳細情報を提供するページが読み込まれます。

   :::image type="content" source="./media/m365bp-dlppolicyinfo.png" alt-text="顧客コンテンツの DLP ポリシーに関する情報のスクリーンショット。":::

   画面の情報に従って DLP ポリシーを設定します。

Microsoft 365 for business のコンプライアンス機能の詳細については、[Microsoft Purview のドキュメント](../compliance/index.yml)を参照してください。

## <a name="use-sensitivity-labels"></a>秘密度ラベルを使用する

秘密度ラベルは、Office アプリ (Outlook、Word、Excel、PowerPoint など) で使用できます。 ラベルの例を次に示します。

- 標準
- 個人
- プライベート
- 社外秘

ただし、会社の他のラベルも定義できます。

秘密度ラベルの使用を開始するには、次の記事を使用します。

1. [秘密度ラベルの詳細](../compliance/sensitivity-labels.md)。

2. [秘密度ラベルの使用を開始する](../compliance/get-started-with-sensitivity-labels.md)。

3. [秘密度ラベルとそのポリシーを作成して構成する](../compliance/create-sensitivity-labels.md)。

4. [秘密度ラベルの使用方法を社内のユーザーに表示する](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。