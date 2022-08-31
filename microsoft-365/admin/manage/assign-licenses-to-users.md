---
title: Microsoft 365 管理センターでユーザーにライセンスを割り当てる
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- commerce_licensing
- VSBFY23
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- business_assist
- okr_SMB
- manage_licenses
- AdminTemplateSet
search.appverid: MET150
description: 製品ライセンスを特定のユーザーに割り当てるのか、またはユーザー ライセンスを特定の製品に割り当てるのかによって、ライセンスを割り当てます。
ms.date: 07/12/2022
ms.openlocfilehash: c004364050c434666f1d0b2d872bddc9040dc1a7
ms.sourcegitcommit: adc4e5707aa074fc4aa0cb9e8c2986fc8b88813c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67112375"
---
# <a name="assign-microsoft-365-licenses-to-users"></a>Microsoft 365 ライセンスをユーザーに割り当てる

[**アクティブなユーザー**] ページまたは [**ライセンス**] ページで、ユーザーにライセンスを割り当てることができます。 使用する方法は、製品ライセンスを特定のユーザーに割り当てるのか、またはユーザー ライセンスを特定の製品に割り当てるのかによって異なります。

> [!NOTE]
> 
> - 管理者は、組織内のユーザーが購入したセルフサービス購入サブスクリプションのライセンスを割り当てたり割り当て解除したりすることはできません。 [セルフサービス購入サブスクリプションを引き継ぐと](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)、ライセンスの割り当てまたは割り当て解除を行うことができるようになります。
> - 一部のサブスクリプションでは、サブスクリプションを購入または更新した後、限られた時間内にのみキャンセルできます。 キャンセル期間が過ぎた場合は、定期的な請求をオフにして、期間の終了時にサブスクリプションをキャンセルします。

[ユーザーを追加すると同時にライセンスを割り当てる方法を説明します](../add-users/add-users.md)。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="before-you-begin"></a>はじめに

- ライセンスを割り当てるには、グローバル管理者、ライセンス管理者、またはユーザー管理者である必要があります。詳細については「[Microsoft 365 の管理者ロールについて](../add-users/about-admin-roles.md)」を参照してください。
- [Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)ことができます。
- グループ ベースのライセンスを使用するには、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](/azure/active-directory/users-groups-roles/licensing-groups-assign)」を参照してください。
- Sway などの一部のサービスでは、ユーザーに自動的に割り当てられるため、個別に割り当てる必要はありません。

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>[ライセンス] ページを使用して、ユーザーにライセンスを割り当てる

**[ライセンス]** ページでは、一度に最大 20 人のユーザーに対して、ライセンスを割り当てることや、ライセンスの割り当てを解除することができます。 このページには、所有している製品、各製品の使用可能ライセンスの数、および使用可能ライセンスの合計数のうちの割り当て済みライセンスの数が表示されます。

**[ライセンス]** ページには、同じ製品名のすべてのサブスクリプションのライセンスの合計が表示されます。 たとえば、 Microsoft 365 Business Premium の、5 つのライセンスがあるサブスクリプションと、同一製品の、8 つのライセンスがある別のサブスクリプションを所有しているとします。 **[ライセンス]** ページには、すべてのサブスクリプションを合わせて、Microsoft 365 Business Premium のライセンスが 13 個あることが示されます。 これは、**[お使いの製品]** ページに表示される内容とは異なります。そのページでは、同一製品のサブスクリプションを複数所有している場合でもサブスクリプションごとに行が表示されます。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

2. 製品を選択します。

3. 製品の詳細ページで、[**ライセンスの割り当て**] を選択します。

4. **[ユーザーにライセンスを割り当てる]** ウィンドウで、名前の入力を開始し、結果から名前を選択して一覧に追加します。一度に最大 20 ユーザーまで追加できます。

5. 特定のアイテムへのアクセス権を割り当てまたは削除するには、[**アプリとサービスをオンまたはオフにする**] を選択します。

6. 完了したら、**[割り当てる]** を選択し、右側のウィンドウを閉じます。

競合が発生した場合は、問題の内容と解決方法を示すメッセージが表示されます。 たとえば、競合するサービスを含むライセンスを選択した場合、各ライセンスに含まれるサービスを確認して再試行するように伝えるエラー メッセージが表示されます。

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>ユーザーがアクセスできるアプリとサービスを変更する

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

2. [**ライセンス**] ページで、特定のユーザーの行を選択します。

3. 右側のウィンドウで、アクセスを許可または削除するアプリとサービスを選択または選択解除します。

4. 完了したら、[**保存**] を選択し、[**閉じる**] を選択します。

## <a name="use-the-active-users-page-to-assign-licenses"></a>[アクティブなユーザー] ページでライセンスを割り当てる

[**アクティブなユーザー**] ページを使用してライセンスを割り当てる場合、ユーザー ライセンスを製品に割り当てます。

### <a name="assign-licenses-to-multiple-users"></a>複数のユーザーにライセンスを割り当てる

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

2. ライセンスを割り当てるユーザー名の横にある円を選択します。

3. 上部にある [**製品ライセンスの管理**] を選択します。

4. [**製品ライセンスの管理**] ウィンドウで、[**さらに割り当てる: 既存のライセンスを保持し、さらに割り当てる**] \> [**次へ**] の順に選択します。

5. [**ライセンス**] で、選択したユーザーに付与するライセンスのボックスを選択します。\
    既定では、そのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。ユーザーが使用できるサービスを制限するには、そのユーザーに設定しないサービスのボックスを [オフ] の位置に切り替えます。

6. ウィンドウの下部にある [**変更の保存**] をクリックします。  
    すべてのユーザーに十分なライセンスがない場合は、追加のライセンスを購入する必要がある場合があります。

> [!NOTE]
> 多数のユーザーにライセンスを割り当てる場合は、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](/azure/active-directory/enterprise-users/licensing-groups-assign)」を使用します

### <a name="assign-licenses-to-one-user"></a>1 人のユーザーにライセンスを割り当てる

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

2. ライセンスを割り当てるユーザーの行を選択します。

3. 右側のウィンドウで、[**ライセンスとアプリ**] を選択します。

4. [**ライセンス**] セクションを展開し、割り当てるライセンスのボックスを選択して、[**変更の保存**] を選択します。

## <a name="assign-a-license-to-a-guest-user"></a>ゲスト ユーザーにライセンスを割り当てる

ゲスト ユーザーを招待して、Azure Active Directory 管理センターで組織と共同作業できます。 ゲスト ユーザーの詳細については、「[Azure Active Directory B2B のゲスト ユーザー アクセスとは](/azure/active-directory/external-identities/what-is-b2b)」を参照してください。 ゲスト ユーザーがいない場合は、「[クイック スタート: Azure Portal のディレクトリにゲスト ユーザーを追加する](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)」を参照してください。

> [!IMPORTANT]
> 次の手順を実行するには、全体管理者である必要があります。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory 管理センター</a>に移動します。

2. ナビゲーション ウィンドウで、**[ユーザー]** を選択します。

3. **[ユーザー | すべてのユーザー (プレビュー)]** ページで **[フィルターの追加]** を選択します。

4. **[フィールドの選択**] メニューから **[ユーザーの種類]** を選択して、**[適用]** を選択します。

5. 次のメニューから **[ゲスト]** を選択します。

6. 結果のリストから、ライセンスが必要なユーザーを選択します。

7. **[管理]** で **[ライセンス]** を選択します。

8. **[割り当て]** を選択します。

9. **[ライセンスの割り当ての更新]** ページで、ライセンスを割り当てる製品を選択します。

10. 右側で、ゲスト ユーザーにアクセスを許可しないサービスのチェック ボックスをオフにします。

11. **[保存]** を選択します。

## <a name="next-steps"></a>次の手順

ユーザーがまだ Office アプリをインストールしていない場合は、「[従業員クイック スタート ガイド](../setup/employee-quick-setup.md)」をユーザーと共有して、ユーザーが「[PC または Mac に Microsoft 365 または Office 2019 をダウンロードしてインストールする方法](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)」や「[モバイル デバイスで Office アプリとメールをセットアップする方法](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)」などを参照してセットアップできるようにします。

## <a name="related-content"></a>関連コンテンツ

[サブスクリプションとライセンスを理解する](../../commerce/licenses/subscriptions-and-licenses.md) (記事)\
[ユーザーからライセンスの割り当てを解除する](remove-licenses-from-users.md) (記事)\
[スクリプションのライセンスを購入または削除する](../../commerce/licenses/buy-licenses.md) (記事)
