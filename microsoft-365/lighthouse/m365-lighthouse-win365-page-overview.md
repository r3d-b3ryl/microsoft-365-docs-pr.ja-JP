---
title: Microsoft 365 Lighthouseの [Windows 365 (クラウド PC)] ページの概要
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: katmartin
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、Windows 365 (クラウド PC) ページについて説明します。
ms.openlocfilehash: b96660f2666d7edce383a1d2e222e23d9b17a5b3
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66017468"
---
# <a name="overview-of-the-windows-365-cloud-pcs-page-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseの [Windows 365 (クラウド PC)] ページの概要  
  
Windows 365は、Microsoft エンドポイント マネージャー (MEM) 管理者がWindows 365 ライセンスを持つユーザーに対してクラウド PC をプロビジョニングおよび管理できるようにするクラウドベースのサービスです。 Windows 365は、デバイス管理用の MEM と完全に統合されており、すべての顧客テナントでクラウド PC のパートナー管理を行うためのMicrosoft 365 Lighthouseがあります。

Windows 365の詳細については、「[Windows 365とは」](/windows-365/overview)を参照してください。 Windows 365要件の一覧については、「[Windows 365の要件」を](/windows-365/enterprise/requirements)参照してください。

> [!IMPORTANT]
> Lighthouse で管理するには、 [MEM](https://go.microsoft.com/fwlink/p/?linkid=2150463) に移動して顧客テナントごとにクラウド PC をプロビジョニングする必要があります。 Lighthouse 内からプロビジョニングすることはできません。

顧客テナント用にクラウド PC をプロビジョニングすると、Microsoft 365 ホーム ページのWindows 365 カードに、プロビジョニングに失敗したクラウド PC の数や Azure ネットワーク接続エラーなど、アクションが必要なクラウド PC に関する簡単なアラートが表示されます。 詳細な状態を取得するには、Windows 365 カードのボタンを選択します (または、左側のナビゲーション ウィンドウで **Windows 365** を選択)、Windows 365 ページを開きます。 このページでは、顧客テナントに割り当てられているクラウド PC の状態の概要を確認したり、管理するすべてのクラウド PC と割り当てられているテナントの一覧を表示したり、顧客テナントとAzure Active Directory (Azure AD) 間の Azure ネットワーク接続とその状態を表示したりできます。

## <a name="overview-tab"></a>[概要] タブ

[概要] タブの色付きカウント注釈バーには、すべての顧客テナントに対するクラウド PC または Azure ネットワーク接続の合計数が表示されます。ネットワーク接続の失敗、未プロビジョニング、プロビジョニングが失敗し、プロビジョニングが間もなく解除されます。

注釈バーの下の一覧で、各顧客テナントの Cloud PC の状態の内訳を確認できます。 特定の状態の Cloud PC を持つテナントを確認するには、カウント注釈バーからその状態を選択してリストをフィルター処理します。 1 つ以上の特定の顧客テナントの Cloud PC の状態を表示するには、[ **テナント** ] ドロップダウン メニューを使用して一覧をフィルター処理します。

特定の顧客テナントの詳細な状態情報を取得するには、そのテナントの状態列の下にある値を選択します。 値の列に応じて、 **Azure ネットワーク接続** または **[すべてのクラウド PC** ] タブが開き、詳細が表示されます。

[概要] タブには、次のオプションも含まれています。

- **更新：** 最新のクラウド PC データを取得する場合に選択します。
- **エクスポート：** Excelコンマ区切り値 (.csv) ファイルに Cloud PC データをエクスポートする場合に選択します。
- **検索：** キーワードを入力して、一覧内の特定の Cloud PC をすばやく見つけます。

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/win365-overview-tab.png" alt-text="[Windows 365概要] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-win365-page-overview/win365-overview-tab.png":::

## <a name="all-cloud-pcs-tab"></a>[すべてのクラウド PC] タブ

[すべてのクラウド PC] タブの色付きカウント注釈バーには、プロビジョニング済み、未プロビジョニング、プロビジョニングに失敗し、プロビジョニングが間もなく解除された状態のすべての顧客テナントにわたるクラウド PC の合計数が表示されます。

すべてのクラウド PC とそのプロビジョニングの状態は、注釈バーの下の一覧で確認できます。 次の情報が提供されます。

- **クラウド PC 名:** クラウド PC に割り当てられた名前。
- **ユーザー：** クラウド PC がプロビジョニングまたはプロビジョニングを試みたユーザー。
- **デバイス名:** Intuneデバイス名。Cloud PC の一意の識別子。
- **テナント：** クラウド PC がプロビジョニングされたカスタマー テナント。
- **ステータス：** Cloud PC のプロビジョニング状態。
- **ライセンスの種類:** Enterpriseまたは Business。
- **仕様：** クラウド PC ハードウェア構成。

特定のプロビジョニング状態のクラウド PC を持つテナントを確認するには、カウント注釈バーからその状態を選択してリストをフィルター処理します。 1 つ以上の特定の顧客テナントの Cloud PC プロビジョニングの状態を表示するには、[ **テナント** ] ドロップダウン メニューを使用して一覧をフィルター処理します。

一覧から任意のクラウド PC を選択して、詳細を表示し、次のような管理アクションを実行します。
- **再起動：** デバイスを再起動する場合に選択します。 
- **再プロビジョニング:** デバイスをリセットする場合に選択します。 Microsoft エンドポイント マネージャー リンクでプロビジョニング ポリシーを表示することもできます。
- **変更：** ユーザーに割り当てられているデバイスの名前を変更する場合に選択します。

[すべてのクラウド PC] タブには、次のオプションも含まれています。

- **エクスポート：** Excelコンマ区切り値 (.csv) ファイルに Cloud PC データをエクスポートする場合に選択します。
- **更新：** 最新のクラウド PC データを取得する場合に選択します。
- **検索：** キーワードを入力して、一覧内の特定の Cloud PC をすばやく見つけます。

Cloud PC プロビジョニングの状態とその意味の完全な一覧については、Windows 365ドキュメント ライブラリの[クラウド PC のデバイス管理の概要](/windows-365/enterprise/device-management-overview#column-details)に関するページを参照してください。

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/all-cloud-pcs-tab.png" alt-text="[すべてのクラウド PC] タブWindows 365スクリーンショット。" lightbox="../media/m365-lighthouse-win365-page-overview/all-cloud-pcs-tab.png":::

## <a name="azure-network-connections-tab"></a>[Azure ネットワーク接続] タブ

[Azure ネットワーク接続] タブの色付きカウント注釈バーには、クラウド PC がWindows 365 Enterpriseされている顧客テナント全体の Azure ネットワーク接続の合計数が表示され、接続の成功と失敗の状態が表示される場合があります。

count 注釈バーの下の一覧で、すべての Azure ネットワーク接続とその接続状態を表示できます。

特定のプロビジョニング状態の接続を表示するには、カウント注釈バーからその状態を選択してリストをフィルター処理します。 1 つ以上の特定の顧客テナントの接続状態を表示するには、[ **テナント** ] ドロップダウン メニューを使用して一覧をフィルター処理します。

一覧でアクションを実行するか、接続のトラブルシューティングを行う必要がある場合は、[**Microsoft エンドポイント マネージャーで接続の詳細を表示する**] を選択します。

[Azure ネットワーク接続] タブには、次のオプションも含まれています。

- **エクスポート：** Excelコンマ区切り値 (.csv) ファイルに接続データをエクスポートする場合に選択します。
- **更新：** 最新の接続データを取得する場合に選択します。
- **検索：** キーワードを入力して、特定の接続をすばやく見つけます。

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/azure-network-connections-tab.png" alt-text="[Azure ネットワーク接続] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-win365-page-overview/azure-network-connections-tab.png":::

## <a name="related-content"></a>関連コンテンツ

[Windows 365 とは](/windows-365/overview) (記事)\
[クラウド PC のWindows 365デバイス管理の概要](/windows-365/enterprise/device-management-overview) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)