---
title: ユーザーの脅威保護を強化Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: コンプライアンス機能を設定して、データ損失を防止し、お客様と顧客の機密情報を安全に保ちます。
ms.openlocfilehash: baac8bc1ad9a425ad7219a1e76949286858f60e0
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403734"
---
# <a name="set-up-compliance-features"></a>コンプライアンス機能をセットアップする

サブスクリプションMicrosoft 365 Business Premiumコンプライアンス機能とプライバシー機能が含まれます。 これらの機能は、会社のデータを保護し、お客様と顧客の機密情報を安全に保つのに役立ちます。 この記事は、コンプライアンス機能を使い始めるのに役立ちます。

## <a name="before-you-begin"></a>はじめに

次のいずれかの役割が割り当てられているか確認Azure Active Directory。

- グローバル管理者
- コンプライアンス管理者

詳細については、「役割の使用 [を開始する」ページを参照してください](../add-users/admin-roles-page.md)。

## <a name="use-compliance-manager-to-get-started"></a>コンプライアンス マネージャーを使用して開始する

:::image type="content" source="../../business-premium/media/m365bp-compliancemanager.png" alt-text="[コンプライアンス マネージャー] のスクリーンショットをMicrosoft 365 Business Premium。":::

Microsoft 365 Business Premiumコンプライアンス マネージャーが含まれています。コンプライアンス機能のセットアップを開始するのに役立ちます。 このような機能には、データ損失防止、情報ガバナンス、インサイダーリスク管理が含まれます。 コンプライアンス マネージャーは、推奨事項、コンプライアンス スコア、スコアを向上させる方法を強調表示することで、時間を節約できます。

開始する方法を次に示します。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com) に移動し、サインインします。

2. ナビゲーション ウィンドウで、[コンプライアンス マネージャー] **を選択します**。

3. [概要 **] タブ** で、情報を確認します。 アイテムまたはリンクを選択して、詳細を表示したり、データ損失防止 (DLP) ポリシーの構成などのアクションを実行したりします。 たとえば、[スコアに影響 **を** 与えるソリューション] セクションで、[残りのアクション] 列でリンク **を選択** できます。

   :::image type="content" source="../../business-premium/media/m365bp-compliancesolutions.png" alt-text="[スコア] ウィンドウに影響を与えるソリューションのスクリーンショット。":::

   このアクションを実行すると、[ **改善アクション]** タブが表示され、選択したアイテムに対してフィルター処理されます。 この例では、構成する DLP ポリシーについて説明します。

   :::image type="content" source="../../business-premium/media/m365bp-dlppoliciestoconfigure.png" alt-text="構成する DLP ポリシーのスクリーンショット。":::

4. [改善アクション **] タブ** で、アイテムを選択します。 この例では、[カスタマイズされた DLP ポリシーまたは個人を特定できる情報を作成する **] を選択しました**。 構成するポリシーの詳細を示すページが読み込まれます。

   :::image type="content" source="../../business-premium/media/m365bp-dlppolicyinfo.png" alt-text="顧客コンテンツの DLP ポリシーに関する情報のスクリーンショット。":::

   画面上の情報に従って DLP ポリシーを設定します。

ビジネス向けコンプライアンス機能の詳細については、「Microsoft 365コンプライアンスドキュメント[Microsoft 365参照してください](../../compliance/index.yml)。

## <a name="use-sensitivity-labels"></a>感度ラベルを使用する

感度ラベルは、Officeアプリ (Outlook、Word、Excel、PowerPoint) で使用できます。 ラベルの例を次に示します。

- 標準
- 個人
- プライベート
- 社外秘

ただし、会社の他のラベルも定義できます。

次の記事を使用して、感度ラベルの使用を開始します。

1. [感度ラベルとは何ですか?](../../compliance/sensitivity-labels.md)

2. [感度ラベルの作成を開始する](../../compliance/get-started-with-sensitivity-labels.md)

3. [公開の感度ラベルとそのポリシー](../../compliance/create-sensitivity-labels.md)

4. [会社のユーザーに、感度ラベルの使い方を表示する](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)