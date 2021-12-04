---
title: Microsoft 365 Lighthouse コンプライアンス ページの概要
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
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouseデバイスコンプライアンス ページについて説明します。
ms.openlocfilehash: d1c4cb8fde2d3f653e77020e4ad29f70da266a06
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302352"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a>Microsoft 365 Lighthouse コンプライアンス ページの概要

> [!NOTE]
> この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。 組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。

Microsoft 365 Lighthouse左側のナビゲーション ウィンドウで [デバイス] を選択して [デバイスコンプライアンス] ページを開き、すべての顧客テナントの Intune デバイスコンプライアンスに関連する分析情報と情報を表示できます。 このページでは、テナント全体のコンプライアンス状態の概要を取得し、テナントごとにデバイスの一覧を表示し、コンプライアンス ポリシーと設定に関する状態レポートを取得できます。

## <a name="overview-tab"></a>[概要] タブ  
  
[概要] タブで、テナント全体のデバイス コンプライアンスの状態を表示し、毎月のデバイス コンプライアンスの傾向を確認し、デバイスにコンプライアンス ポリシーが割り当てられているかどうかを追跡できます。 条件付きアクセス ポリシーを使用して、デバイスコンプライアンス要件が適用されていないテナントの数も確認できます。 [詳細を表示 **] を選択すると** 、詳細を表示できます。

特定の顧客テナントのデバイスコンプライアンスに関する詳細な情報を取得するには、そのテナントの状態列の下の値を選択します。 [デバイス] タブが開き、選択したテナントのデバイスコンプライアンスの詳細を表示できます。

デバイス コンプライアンス データをコンマ区切りExcel (.csv) ファイルにエクスポートするには、[エクスポート] を **選択します**。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="[概要] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png":::

## <a name="devices-tab"></a>[デバイス] タブ

[デバイス] タブで、色付きカウント注釈バーには、コンプライアンス状態が [準拠]、[非準拠]、猶予期間、および評価されていないすべての顧客テナントのデバイスの総数が表示されます。 さまざまなコンプライアンス状態の詳細については [、「Monitor Intune Device compliance policies」を参照してください](/mem/intune/protect/compliance-policy-monitor)。

特定のコンプライアンス状態のデバイスを持つテナントを確認するには、カウント注釈バーからその状態を選択してリストをフィルター処理します。 1 つ以上の特定の顧客テナントのデバイスコンプライアンスの状態を確認するには、[テナント] ドロップダウン メニューを使用してリストをフィルター処理します。

リスト内の任意のデバイス名を選択して、そのデバイスの現在のコンプライアンス状態の詳細を表示します。 デバイスを同期または再起動するか、[デバイスの表示] を選択Microsoft エンドポイント マネージャートラブルシューティングまたは追加のアクションを実行する必要がある場合は、[デバイスの表示] を選択します。

> [!NOTE]
> デバイスを再起動すると、デバイスの所有者に自動的に通知が送信され、保存されていない作業が失われる可能性があります。 このため、デバイスを再起動する前に、デバイスの所有者に通知することができます。

[デバイス] タブには、次のオプションも含まれています。

- **エクスポート:** デバイス コンプライアンス データをコンマ区切り (Excel) ファイルにエクスポート.csvします。
- **更新:** 最新のデバイス コンプライアンス データを取得する場合に選択します。
- **同期:** [非準拠]、[猶予期間内]、または [評価されていない] の状態の一覧から 1 つ以上のデバイスを選択し、このオプションを選択して、それらのデバイスに Intune にチェックインし、割り当てられているポリシーを直ちに受信します。
- **再起動:** 状態が [非準拠]、猶予期間、または評価されない状態の一覧から 1 つ以上のデバイスを選択し、これらのデバイスを再起動するには、このオプションを選択します。
- **検索:** キーワードを入力して、リスト内の特定のデバイスをすばやく検索します。
 
:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="[デバイス] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png":::

## <a name="policies-tab"></a>[ポリシー] タブ

[ポリシー] タブで、テナント全体のデバイス コンプライアンス ポリシーを表示し、[比較] オプションを使用して、同じプラットフォームの種類の 2 つまたは 3 つのポリシー **を比較** できます。

特定のプラットフォーム上のデバイスのポリシーを表示するには **、OS** ドロップダウン メニューを使用してリストをフィルター処理します。 1 つ以上の特定の顧客テナントのポリシーを表示するには、[ **テナント** ] ドロップダウン メニューを使用してリストをフィルター処理します。

リスト内のポリシー名を選択して、そのポリシーの詳細を表示します。 アクションを実行する必要がある場合、または追加情報を表示する必要がある場合は、[このポリシーを表示する] を選択 **Microsoft エンドポイント マネージャー。**

[ポリシー] タブには、次のオプションも含まれています。

- **エクスポート:** デバイス コンプライアンス ポリシー データをコンマ区切りExcel (.csv) ファイルにエクスポートする場合に選択します。
- **更新:** 最新のデバイス コンプライアンス ポリシー データを取得する場合に選択します。
- **検索:** キーワードを入力して、リスト内の特定のデバイス コンプライアンス ポリシーをすばやく見つける。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="[ポリシー] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png":::

## <a name="settings-tab"></a>設定タブ

[設定] タブには、テナント デバイス間の非準拠設定の集計レポートが表示されます。 

特定のプラットフォーム上のデバイスの非準拠設定を表示するには、[プラットフォーム] ドロップダウン メニューを使用してリストをフィルター処理します。 1 つ以上の特定の顧客テナントの非準拠設定を表示するには、[ **テナント** ] ドロップダウン メニューを使用してリストをフィルター処理します。

一覧で非準拠の設定名を選択してウィンドウを開き、その特定の非準拠設定を持つデバイスを持つテナントの一覧を表示できます。 ここから、リストから任意のテナントを選択して、特定の非準拠設定を持つそのテナント内のデバイスに関する情報を表示することで、さらにドリルダウンできます。 また、デバイスを同期または再起動するか、[デバイスの表示] を選択Microsoft エンドポイント マネージャートラブルシューティングまたは追加の操作が必要な場合は、[デバイスの表示] を選択します。

[設定] タブには、次のオプションも含まれています。

- **エクスポート:** 非準拠の設定データをコンマ区切Excel (.csv) ファイルにエクスポートする場合に選択します。
- **更新:** 最新の非準拠設定データを取得する場合に選択します。
- **検索:** キーワードを入力して、リスト内の特定の非準拠設定をすばやく見つける。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="[ページ] タブ設定スクリーンショット。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png":::

## <a name="related-content"></a>関連コンテンツ

[Windows 365 (クラウド PC) ページの概要](m365-lighthouse-win365-page-overview.md)(記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
