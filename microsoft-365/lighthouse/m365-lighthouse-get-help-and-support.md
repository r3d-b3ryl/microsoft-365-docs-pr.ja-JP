---
title: ヘルプとサポートを受Microsoft 365 Lighthouse
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
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouseヘルプとサポートを受ける方法について説明します。
ms.openlocfilehash: 24420874314c67b621a53f8eb06e22a49137d380
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314365"
---
# <a name="get-help-and-support-for-microsoft-365-lighthouse"></a>ヘルプとサポートを受Microsoft 365 Lighthouse 

ヘルプが必要な場合は、いくつかのオプションを使用できます。 最初に、既知の問題が発生した場合に確認します。

- 顧客テナント サービスの現在の正常性を確認します。

    1. ライトハウスの左側のナビゲーション ウィンドウで、[サービスの正常性] **を選択します**。 
    2. 現在および過去の問題に関する詳細情報を表示します。

- ライトハウス テナント サービスの現在の正常性を確認します。

    1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の Microsoft 365 管理センターに移動します。
    2. 左側のナビゲーション ウィンドウで、[**HealthService 正常性]** >  **を選択します**。
    3. サービスの一覧で **、Microsoft 365を** 見つけて展開して、スイート内のすべてのサービスを表示します。
    4. [Microsoft 365 Lighthouseを見 **つけて**、正常性を確認します。

- [既知の問題と問題] に問題が一覧表示[Microsoft 365 Lighthouse](/office365/troubleshoot/microsoft-365-lighthouse/lighthouse-known-issues)。

これらのリソースに記載されていない問題が発生している場合は、この記事の手順に従って、セルフ ヘルプ オプションを表示するか、サービス要求を作成します。

## <a name="before-you-begin"></a>始める前に

- サービス要求を作成および管理するには、**microsoft.office365.supportTickets/allEntities/allTasks** というプロパティ セットを使用して、少なくとも 1 つの Azure Active Directory (Azure AD) 役割が割り当てられている必要があります。 役割の一覧Azure AD組み込[Azure ADを参照してください](/azure/active-directory/roles/permissions-reference)。 役割を割り当てる方法については、「ユーザーに役割を割り当Azure AD[割り当てる」を参照してください](/azure/active-directory/roles/manage-roles-portal)。

- サービス要求を作成する必要がある場合は、診断ログ、テナント ID、ユーザー ID (特定のユーザーが影響を受ける場合) など、問題に関する可能な限り多くの詳細を収集します。

## <a name="access-help-and-support"></a>ヘルプとサポートにアクセスする

1.  [ライトハウス] で [ **?** ポータルの上部にあるアイコンをクリックして[ヘルプ] ウィンドウ **を開** き、次のいずれかの操作を行います。
    
    -  問題が発生したポータルのページにある場合は、[診断の表示 **] を選択します**。

        これにより、サポート エージェントが問題のトラブルシューティングに役立つ情報を含む JSON ファイルが作成されます。 ファイルを保存して、サービス要求に添付できます。

        > [!NOTE]
        > JSON ファイルには、個人を特定できる情報が含まれる。

    -  問題がポータルの現在のページに分離されていない場合は、次の手順に進みます。

2.  [ヘルプ **] ウィンドウで** 、[ヘルプとサポート **] ボタンを選択** します。 [方法] **ウィンドウが開** きます。

    > [!NOTE]
    > [ヘルプ **の方法]** ウィンドウが開かない場合は、グローバル管理者のアクセス許可を持つパートナー テナントのユーザーに連絡し、サポートを求める必要があります。

3.  [ヘルプ **の方法] ウィンドウ** で、問題の説明を入力し、Enter キーを押 **します**。 検索結果に関連するヘルプ記事が含まれるMicrosoft 365 Lighthouse製品名の完全な名前を説明に含める必要があります。

4.  推奨される記事の一覧を参照して、問題の解決に役立つ記事を確認してください。

    問題の説明を入力しても、ヘルプ記事の一覧が返されていない場合は、説明を言い換え、別の検索を試してください。

5.  推奨される記事で問題が生じなかった場合は、[サポートに問い **合わせ] を選択します**。

6.  フォームに情報を入力し、手順 1 で保存したスクリーンショットと JSON&nbsp; ファイルを添付して、該当する場合は [連絡する] **を選択します**。 予想される待機時間がウィンドウに表示されます。

## <a name="related-content"></a>関連コンテンツ

[ユーザーに関する既知Microsoft 365 Lighthouse](m365-lighthouse-known-issues.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)\
[Troubleshooot の問題とエラー メッセージをMicrosoft 365 Lighthouseする](m365-lighthouse-troubleshoot.md) (記事)