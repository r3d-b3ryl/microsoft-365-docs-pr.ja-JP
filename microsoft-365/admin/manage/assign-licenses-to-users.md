---
title: ユーザーにライセンスを割り当てる
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
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
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
- AdminTemplateSet
search.appverid: MET150
description: 製品ライセンスを特定のユーザーに割り当てるのか、またはユーザー ライセンスを特定の製品に割り当てるのかによって、ライセンスを割り当てます。
ms.date: 09/16/2021
ms.openlocfilehash: 68124f26037e6d21e9b3f1cb0b7888edc005fe77
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61371102"
---
# <a name="assign-licenses-to-users"></a>ユーザーにライセンスを割り当てる

[**アクティブなユーザー**] ページまたは [**ライセンス**] ページで、ユーザーにライセンスを割り当てることができます。 使用する方法は、製品ライセンスを特定のユーザーに割り当てるのか、またはユーザー ライセンスを特定の製品に割り当てるのかによって異なります。

> [!NOTE]
> 
> - 管理者は、組織内のユーザーが購入したセルフサービス購入サブスクリプションのライセンスを割り当てたり割り当て解除したりすることはできません。 [セルフサービス購入サブスクリプションを引き継ぐと](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)、ライセンスの割り当てまたは割り当て解除を行うことができるようになります。
> - 一部のサブスクリプションでは、サブスクリプションを購入または更新した後、限られた時間内にのみキャンセルできます。 キャンセル期間が過ぎた場合は、定期的な請求をオフにして、期間の終了時にサブスクリプションをキャンセルします。

[ユーザーを追加すると同時にライセンスを割り当てる方法を説明します](../add-users/add-users.md)。

## <a name="before-you-begin"></a>はじめに

- ライセンスを割り当てるには、グローバル管理者、ライセンス管理者、またはユーザー管理者である必要があります。詳細については「[Microsoft 365 の管理者ロールについて](../add-users/about-admin-roles.md)」を参照してください。
- [Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)ことができます。
- グループ ベースのライセンスを使用するには、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](/azure/active-directory/users-groups-roles/licensing-groups-assign)」を参照してください。
- Sway などの一部のサービスでは、ユーザーに自動的に割り当てられるため、個別に割り当てる必要はありません。


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>[ライセンス] ページを使用して、ユーザーにライセンスを割り当てる

[**ライセンス**] ページを使用してライセンスを割り当てる場合、特定の製品のライセンスを最大 20 人のユーザーに割り当てます。 [**ライセンス**] ページに、サブスクリプションがあるすべての製品のリストが表示されます。 また、各製品のライセンスの総数、割り当てられているライセンスの数、および使用可能なライセンスの数も表示されます。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

2. 製品を選択します。

3. 製品の詳細ページで、[**ライセンスの割り当て**] を選択します。

4. **[ユーザーにライセンスを割り当てる]** ウィンドウで、名前の入力を開始し、結果から名前を選択して一覧に追加します。一度に最大 20 ユーザーまで追加できます。

4. 特定のアイテムへのアクセス権を割り当てまたは削除するには、[**アプリとサービスをオンまたはオフにする**] を選択します。

6. 完了したら、**[割り当て]** を選択し、**[閉じる]** を選択します。

競合がある場合、メッセージが表示され、問題の内容と修正方法が示されます。 たとえば、競合するサービスを含むライセンスを選択した場合、各ライセンスに含まれるサービスを確認して再試行するように伝えるエラー メッセージが表示されます。

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

ユーザーがまだ Office アプリをインストールしていない場合は、「[従業員クイック スタート ガイド](../../business-video/employee-quick-setup.md)」をユーザーと共有して、ユーザーが「[PC または Mac に Microsoft 365 または Office 2019 をダウンロードしてインストールする方法](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)」や「[モバイル デバイスで Office アプリとメールをセットアップする方法](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)」などを参照してセットアップできるようにします。

## <a name="related-content"></a>関連コンテンツ

[サブスクリプションとライセンスを理解する](../../commerce/licenses/subscriptions-and-licenses.md) (記事)\
[ユーザーからライセンスの割り当てを解除する](remove-licenses-from-users.md) (記事)\
[スクリプションのライセンスを購入または削除する](../../commerce/licenses/buy-licenses.md) (記事)
