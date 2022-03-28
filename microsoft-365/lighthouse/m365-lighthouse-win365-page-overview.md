---
title: Microsoft 365 Lighthouse Windows 365 (クラウド PC) ページの概要
f1.keywords: CSH
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
description: 管理サービス プロバイダー (MSP) で Microsoft 365 Lighthouse 365 (クラウド PC) ページWindowsを参照してください。
ms.openlocfilehash: fa910e3de992aa3f3f76090f76a473a96aebc8fb
ms.sourcegitcommit: 9d563faeaa50b59b0b468dbb373d886e5270f58e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "64387119"
---
# <a name="windows-365-cloud-pcs-page-overview"></a>Windows 365 (クラウド PC) ページの概要  
  
Windows 365 は、Microsoft エンドポイント マネージャー (MEM) 管理者が、Windows 365 ライセンスを持つユーザーに対してクラウド PC をプロビジョニングおよび管理できるクラウドベースのサービスです。 Windows 365 は、デバイス管理用の MEM と完全に統合され、Microsoft 365 Lighthouse は、すべての顧客テナントでクラウド PC のパートナー管理を行います。

365 の詳細については、「Windows [365 とはWindowsしてください。](/windows-365/overview) 365 の要件Windows一覧については、「[365 の要件Windows参照してください](/windows-365/enterprise/requirements)。

> [!IMPORTANT]
> ライトハウスでクラウド [PC](https://go.microsoft.com/fwlink/p/?linkid=2150463) を管理するには、MEM に移動して顧客テナントごとにクラウド PC をプロビジョニングする必要があります。 ライトハウス内からプロビジョニングを行う必要があります。

顧客テナント用にクラウド PC をプロビジョニングすると、Microsoft 365 ホーム ページの Windows 365 カードは、プロビジョニングに失敗したクラウド PC の数や Azure ネットワーク接続エラーなど、アクションが必要なクラウド PC に関する簡単な通知を提供します。 詳細な状態を取得するには、Windows 365 カードのボタンを選択します (または、左側のナビゲーション ウィンドウで **Windows 365** を選択します)、Windows 365 ページを開きます。 このページでは、顧客テナントに割り当てられたクラウド PC の状態の概要を取得し、管理しているすべてのクラウド PC と、そのテナントが割り当てられているテナントの一覧を表示し、顧客テナントと Azure Active Directory (Azure AD) の間の Azure ネットワーク接続とその状態を表示できます。

## <a name="overview-tab"></a>[概要] タブ

[概要] タブで、色付きカウント注釈バーには、次の状態を持つすべての顧客テナントにおけるクラウド PC または Azure ネットワーク接続の総数が表示されます。ネットワーク接続の失敗、プロビジョニングの失敗、プロビジョニングの失敗、および間もなくプロビジョニング解除が行えます。

各顧客テナントのクラウド PC の状態の内訳は、注釈バーの下の一覧で確認できます。 特定の状態のクラウド PC を持つテナントを確認するには、カウント注釈バーからその状態を選択してリストをフィルター処理します。 1 つ以上の特定の顧客テナントのクラウド PC の状態を確認するには、[テナント] ドロップダウン メニューを使用してリストをフィルター処理します。

特定の顧客テナントの詳細な状態情報を取得するには、そのテナントの状態列の下の値を選択します。 値が含む列に応じて、[ **Azure ネットワーク** 接続] タブまたは [すべてのクラウド **PC** ] タブが開き、詳細が表示されます。

[概要] タブには、次のオプションも含まれています。

- **更新:** 最新のクラウド PC データを取得する場合に選択します。
- **エクスポート:** クラウド PC データをコンマ区切り値 (Excel) ファイルにエクスポート.csvします。
- **検索:** キーワードを入力して、リスト内の特定のクラウド PC をすばやく見つける。

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/win365-overview-tab.png" alt-text="[365 Windows] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-win365-page-overview/win365-overview-tab.png":::

## <a name="all-cloud-pcs-tab"></a>[すべてのクラウド PC] タブ

[すべてのクラウド PC] タブで、色付きカウント注釈バーには、プロビジョニング済み、プロビジョニングされていない、プロビジョニングに失敗した、すぐにプロビジョニング解除という状態のすべての顧客テナントのクラウド PC の総数が表示されます。

すべてのクラウド PC とそのプロビジョニングの状態は、注釈バーの下の一覧で表示できます。 次の情報が提供されます。

- **クラウド PC 名:** クラウド PC に割り当てられた名前。
- **テナント:** クラウド PC がプロビジョニングされた顧客テナント。
- **デバイス名:** Intune デバイス名: クラウド PC の一意の識別子。
- **PC の種類:** 標準 SKU に従ったクラウド PC の種類。
- **状態:** クラウド PC のプロビジョニング状態。
- **ユーザー:** クラウド PC がプロビジョニングまたはプロビジョニングを試みたユーザー。

特定のプロビジョニング状態のクラウド PC を持つテナントを確認するには、カウント注釈バーからその状態を選択してリストをフィルター処理します。 1 つ以上の特定の顧客テナントのクラウド PC プロビジョニングの状態を確認するには、[テナント] ドロップダウン メニューを使用してリストをフィルター処理します。

詳細を表示するには、一覧でクラウド PC を選択します。 クラウド PC でアクションを実行する必要がある場合は、テナント プロビジョニング ポリシーとデバイスの詳細をクラウド PC で表示Microsoft エンドポイント マネージャー。

[すべてのクラウド PC] タブには、次のオプションも含まれています。

- **更新:** 最新のクラウド PC データを取得する場合に選択します。
- **エクスポート:** クラウド PC データをコンマ区切り値 (Excel) ファイルにエクスポート.csvします。
- **検索:** キーワードを入力して、リスト内の特定のクラウド PC をすばやく見つける。
- **プロビジョニングの再試行:** 状態が [プロビジョニングに失敗しました] の一覧から 1 ~ 20 のクラウド PC を選択し、このオプションを選択して、それらのクラウド PC のプロビジョニングを再試行します。

クラウド PC プロビジョニングの状態と、その意味の完全な一覧については、「Windows 365 ドキュメント ライブラリ」を参照してください。[](/windows-365/enterprise/device-management-overview#column-details)

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/all-cloud-pcs-tab.png" alt-text="[365 Windowsクラウド PC] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-win365-page-overview/all-cloud-pcs-tab.png":::

## <a name="azure-network-connections-tab"></a>[Azure ネットワーク接続] タブ

[Azure ネットワーク接続] タブで、色付きカウント注釈バーに、成功した接続と失敗した接続の状態を持つすべての顧客テナント間の Azure ネットワーク接続の総数が表示されます。

カウント注釈バーの下の一覧で、すべての Azure ネットワーク接続とその接続状態を表示できます。

特定のプロビジョニング状態の接続を表示するには、カウント注釈バーからその状態を選択してリストをフィルター処理します。 1 つ以上の特定の顧客テナントの接続状態を表示するには、[テナント] ドロップダウン メニューを使用してリストをフィルター処理します。

一覧でアクションを実行したり、接続のトラブルシューティングを行う必要がある場合は、[接続の詳細を表示する] を選択 **Microsoft エンドポイント マネージャー。**

[Azure ネットワーク接続] タブには、次のオプションも含まれています。

- **更新:** 最新の接続データを取得する場合に選択します。
- **エクスポート:** 接続データをコンマ区切り (Excel) ファイルにエクスポート.csvします。
- **検索:** キーワードを入力して、特定の接続をすばやく見つける。

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/azure-network-connections-tab.png" alt-text="[Azure ネットワーク接続] タブのスクリーンショット。" lightbox="../media/m365-lighthouse-win365-page-overview/azure-network-connections-tab.png":::

## <a name="related-content"></a>関連コンテンツ

[Windows 365 とは](/windows-365/overview) (記事)\
[Windows PC の 365 デバイス](/windows-365/enterprise/device-management-overview)管理の概要 (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)