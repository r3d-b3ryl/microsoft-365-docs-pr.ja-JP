---
title: Microsoft 365 Lighthouseのヘルプとサポートを受ける
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: crimora
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、ヘルプとサポートを受ける方法について説明します。
ms.openlocfilehash: 5bf61e9563a87ac44219c1c4644153ce98755cb5
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66017808"
---
# <a name="get-help-and-support-for-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseのヘルプとサポートを受ける 

ヘルプが必要な場合は、いくつかのオプションを使用できます。 最初に、既知の問題があるかどうかを確認します。

- カスタマー テナント サービスの現在の正常性を確認します。

    1. Lighthouse の左側のナビゲーション ウィンドウで、**サービス正常性** を選択します。 
    2. 現在の問題と過去の問題に関する詳細情報を表示します。

- Lighthouse テナント サービスの現在の正常性を確認します。

    1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の Microsoft 365 管理センターに移動します。
    2. 左側のナビゲーション ウィンドウで、[**正常性** > **サービス正常性] を** 選択します。
    3. サービスの一覧で **、Microsoft 365 スイート** を見つけて展開し、スイート内のすべてのサービスを表示します。
    4. **Microsoft 365 Lighthouse** を見つけて正常性を確認します。

- Microsoft 365 Lighthouseに[関する既知の問題に問題](/office365/troubleshoot/microsoft-365-lighthouse/lighthouse-known-issues)が一覧表示されているかどうかを確認します。

これらのリソースに一覧にない問題が発生した場合は、この記事の手順に従ってセルフ ヘルプ オプションを表示するか、サービス要求を作成します。

## <a name="before-you-begin"></a>はじめに

- サービス要求を作成および管理するには、**microsoft.office365.supportTickets/allEntities/allTasks** というプロパティ セットを使用して、少なくとも 1 つのAzure Active Directory (Azure AD) ロールが割り当てられている必要があります。 Azure AD ロールの一覧については、 [Azure AD の組み込みロールに](/azure/active-directory/roles/permissions-reference)関するページを参照してください。 ロールを割り当てる方法については、「 [ユーザーに Azure AD ロールを割り当てる」を参照してください](/azure/active-directory/roles/manage-roles-portal)。

- サービス要求を作成する必要がある場合は、診断ログ、テナント ID、ユーザー ID (特定のユーザーが影響を受ける場合) など、問題に関するできるだけ多くの詳細を収集します。

## <a name="access-help-and-support"></a>ヘルプとサポートにアクセスする

1.  Lighthouse で、 **?** アイコンをクリックして **ヘルプ** ウィンドウを開き、次のいずれかの操作を行います。
    
    -  問題が発生したポータルのページにある場合は、[診断の表示] を選択 **します**。

        これにより、サポート エージェントが問題のトラブルシューティングに役立つ情報を含む JSON ファイルが作成されます。 ファイルを保存して、サービス要求に添付できるようにします。

        > [!NOTE]
        > JSON ファイルには、個人を特定できる情報が含まれます。

    -  問題がポータルの現在のページに分離されていない場合は、次の手順に進みます。

2.  **[ヘルプ**] ウィンドウで、[**ヘルプとサポート**] ボタンを選択します。 [ヘルプの **方法** ] ウィンドウが開きます。

    > [!NOTE]
    > [ **ヘルプの方法]** ウィンドウが開かない場合は、グローバル管理者のアクセス許可を持つパートナー テナントのユーザーに連絡し、サポートを依頼する必要があります。

3.  [ **ヘルプの方法** ] ウィンドウで、問題の説明を入力し、Enter キーを押 **します**。 検索結果に関連するヘルプ記事が含まれるように、説明に完全な製品名 *Microsoft 365 Lighthouse* を含めることをお勧めします。

4.  推奨される記事の一覧を確認して、問題の解決に役立つ記事があるかどうかを確認してください。

    問題の説明を入力し、ヘルプ記事の一覧が返されない場合は、説明を言い換えて別の検索を試してください。

5.  推奨される記事が役に立たない場合は、[ **サポートにお問い合わせください**] を選択します。

6.  フォームに情報を入力し、手順&nbsp;1 で保存したスクリーンショットと JSON ファイル (該当する場合) を添付し、[ **お問い合わせ**] を選択します。 予期される待機時間がウィンドウに表示されます。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouseに関する既知の問題](m365-lighthouse-known-issues.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)\
[Microsoft 365 Lighthouseでの問題とエラー メッセージのトラブルシューティングと解決](m365-lighthouse-troubleshoot.md) (記事)