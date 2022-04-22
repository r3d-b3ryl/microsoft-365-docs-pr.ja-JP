---
title: Microsoft 365 Lighthouseの [デバイス コンプライアンス] ページの概要
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、デバイス コンプライアンス ページについて説明します。
ms.openlocfilehash: e5440d89a34593655076cb91a348a176590dc52f
ms.sourcegitcommit: 339d2c2ffea06726f69429f73c1113c649f37b18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65023703"
---
# <a name="overview-of-the-device-compliance-page-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseの [デバイス コンプライアンス] ページの概要

Microsoft 365 Lighthouseでは、左側のナビゲーション ウィンドウで **[デバイス**] を選択して [デバイス コンプライアンス] ページを開くことで、すべての顧客テナントのデバイス コンプライアンスIntune関連する分析情報と情報を表示できます。 このページでは、テナント間のコンプライアンス状態の概要を確認したり、各テナントのデバイスの一覧を表示したり、コンプライアンス ポリシーと設定に関する状態レポートを取得したりできます。

## <a name="overview-tab"></a>[概要] タブ  
  
[概要] タブでは、テナント全体のデバイス コンプライアンスの状態を表示し、毎月のデバイス コンプライアンスの傾向を確認し、デバイスにコンプライアンス ポリシーが割り当てられているかどうかを追跡できます。 条件付きアクセス ポリシーを使用して、デバイス コンプライアンス要件が適用されていないテナントの数も確認できます。 [詳細の **表示** ] を選択すると、詳細を表示できます。

特定の顧客テナントの詳細なデバイス コンプライアンス情報を取得するには、そのテナントの状態列の下にある値を選択します。 選択したテナントのデバイス コンプライアンスの詳細を表示できるように、[デバイス] タブが開きます。

デバイス コンプライアンス データをExcelコンマ区切り値 (.csv) ファイルにエクスポートするには、[**エクスポート**] を選択します。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="[概要] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png":::

## <a name="devices-tab"></a>[デバイス] タブ

[デバイス] タブの色付きカウント注釈バーには、コンプライアンス状態が[準拠]、[非準拠]、[猶予期間]、および [未評価] のすべての顧客テナントのデバイスの合計数が表示されます。 さまざまなコンプライアンス状態の詳細については、「[デバイス コンプライアンス ポリシー Intune監視](/mem/intune/protect/compliance-policy-monitor)する」を参照してください。

特定のコンプライアンス状態のデバイスを持つテナントを確認するには、カウント注釈バーからその状態を選択して一覧をフィルター処理します。 1 つ以上の特定の顧客テナントのデバイス コンプライアンスの状態を表示するには、[ **テナント** ] ドロップダウン メニューを使用して一覧をフィルター処理します。

一覧から任意のデバイス名を選択すると、そのデバイスの現在のコンプライアンス状態の詳細が表示されます。 デバイスを同期または再起動するか、トラブルシューティングや追加のアクションを実行する必要がある場合 **は、[Microsoft エンドポイント マネージャーでデバイスを表示** する] を選択します。

> [!NOTE]
> デバイスを再起動すると、デバイス所有者に自動的に通知が届かないので、未保存の作業が失われる可能性があります。 このため、デバイスを再起動する前に、デバイスの所有者に通知することが必要になる場合があります。

[デバイス] タブには、次のオプションも含まれています。

- **エクスポート：** デバイス コンプライアンス データをExcelコンマ区切り値 (.csv) ファイルにエクスポートする場合に選択します。
- **更新：** 最新のデバイス コンプライアンス データを取得する場合に選択します。
- **同期：** 状態が [非準拠]、[猶予期間中]、または [未評価] の一覧から 1 つ以上のデバイスを選択し、これらのデバイスにIntuneでチェックインし、割り当てられているポリシーを直ちに受信するように強制するには、このオプションを選択します。
- **再起動：** 状態が [非準拠]、[猶予期間中]、または [未評価] の一覧から 1 つ以上のデバイスを選択し、このオプションを選択してデバイスを再起動します。
- **検索：** キーワードを入力して、一覧内の特定のデバイスをすばやく見つけます。
 
:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="[デバイス] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png":::

## <a name="policies-tab"></a>[ポリシー] タブ

[ポリシー] タブでは、[比較] オプションを使用して、テナント全体のデバイス コンプライアンス ポリシーを表示し、同じプラットフォームの種類の 2 つまたは 3 つのポリシーを **比較** できます。

特定のプラットフォーム上のデバイスのポリシーを表示するには、 **OS** ドロップダウン メニューを使用して一覧をフィルター処理します。 1 つ以上の特定の顧客テナントのポリシーを表示するには、[ **テナント** ] ドロップダウン メニューを使用して一覧をフィルター処理します。

一覧から任意のポリシー名を選択すると、そのポリシーの詳細が表示されます。 アクションを実行する必要がある場合、または追加情報を表示する必要がある場合は、[**Microsoft エンドポイント マネージャーでこのポリシーを表示する**] を選択します。

[ポリシー] タブには、次のオプションも含まれています。

- **エクスポート：** デバイス コンプライアンス ポリシー データをExcelコンマ区切り値 (.csv) ファイルにエクスポートする場合に選択します。
- **更新：** 最新のデバイス コンプライアンス ポリシー データを取得する場合に選択します。
- **検索：** キーワードを入力して、一覧内の特定のデバイス コンプライアンス ポリシーをすばやく見つけます。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="[ポリシー] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png":::

## <a name="settings-tab"></a>[設定] タブ

[設定] タブには、テナント デバイス間の非準拠設定の集計レポートが表示されます。 

特定のプラットフォーム上のデバイスの非準拠設定を表示するには、[ **プラットフォーム** ] ドロップダウン メニューを使用して一覧をフィルター処理します。 1 つ以上の特定の顧客テナントの非準拠設定を表示するには、[ **テナント** ] ドロップダウン メニューを使用して一覧をフィルター処理します。

一覧で非準拠の設定名を選択すると、その特定の非準拠設定を持つデバイスがあるテナントの一覧を表示できるウィンドウが開きます。 ここから、一覧から任意のテナントを選択して、特定の非準拠設定を持つそのテナント内のデバイスに関する情報を表示することで、さらにドリルダウンできます。 デバイスを同期または再起動したり、トラブルシューティングを行ったり、さらにアクションを実行したりする必要がある場合 **は、[Microsoft エンドポイント マネージャーでデバイスを表示** する] を選択することもできます。

[設定] タブには、次のオプションも含まれています。

- **エクスポート：** 非準拠の設定データをExcelコンマ区切り値 (.csv) ファイルにエクスポートする場合に選択します。
- **更新：** 最新の非準拠設定データを取得する場合に選択します。
- **検索：** キーワードを入力して、リスト内の特定の非準拠設定をすばやく見つけます。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="[設定] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png":::

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 LighthouseのWindows 365 (クラウド PC) ページの概要](m365-lighthouse-win365-page-overview.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
