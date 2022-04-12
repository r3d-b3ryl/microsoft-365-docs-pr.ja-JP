---
title: Microsoft から別のホストにドメインを転送する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Microsoft から別のレジストラーにドメインを転送する手順については、こちらをご覧ください。 '
ms.openlocfilehash: 18f2b6502268b757b651abe08585cc06b63d7129
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782481"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Microsoft から別のホストにドメインを転送する

Microsoft からドメインを購入した後、Microsoft 365 ドメインを別のレジストラーに 60 日間譲渡することはできません。

> [!NOTE]
> _Whois_ クエリでは、Microsoft が購入したドメイン レジストラーが Wild West Domains LLC として表示されます。 ただし、ご利用のMicrosoft 365購入済みドメインに関して連絡を受けるのは Microsoft のみです。

次の手順に従って、Microsoft 365でコードを取得し、他のドメイン レジストラー Web サイトに移動して、ドメイン名を新しいレジストラーに転送するように設定します。

## <a name="transfer-a-domain"></a>ドメインを転送する

1. 管理センターで、**設定** \> ドメインに移動 **します**。

2. [**ドメイン**] ページで、別のドメイン レジストラーに転送するMicrosoft 365 ドメインを選択し、[**正常性の確認**] を選択します。

3. ページの上部にある [ **ドメインの転送**] を選択します。

4. [ **ドメインの転送先の選択]** ページで、[ **別のレジストラー**] を選択し、[ **次へ**] をクリックします。

5. [**ドメイン転送のロック解除**] ページで、**_ドメイン_><[転送のロック解除**] を選択し、[**次へ**] を選択します。

6. ドメイン転送の連絡先情報を確認し、[ **次へ**] を選択します。

7. 承認コードをコピーし、ドメイン転送の状態が [**登録]** タブで **[ロック解除]** に変更されるまで約 30 分待ってから、次の手順に進みます。

8. 今後ドメイン名を管理するドメイン レジストラーの Web サイトに移動します。 ドメインを転送するための指示に従います (Web サイトでヘルプを検索してください)。 これは通常、転送料金を支払い、Authcode を新しいレジストラーに渡して、転送を開始できることを意味します。 Microsoft は、転送要求を受け取ったことを確認するために電子メールを送信し、ドメインは 5 日以内に転送されます。

    承認コードの **[登録]** タブは、Microsoft 365 **の [ドメイン]** ページにあります。

    > [!TIP]
    > .uk ドメインには別の手順が必要です。 Microsoft サポートに連絡して、今後ドメインを管理するレジストラーと一致するように **IPS Tag タグを変更** を依頼します。 タグを変更すると、ドメインは直ちに新しいレジストラーに移動します。 転送を完了するには、新しいレジストラーでするべきことがあります。移転手数料を支払って、新しいレジストラーで転送されたドメインをアカウントに追加する必要があります。

9. 移行の完了後は、新しいドメイン レジストラーでドメインの更新を実行します。

10. プロセスを完了するには、管理センターの **[ドメイン** ] ページに戻り、[ **ドメイン転送の完了**] を選択します。 これにより、ドメインがMicrosoft 365から購入されなくなったとマークされ、ドメイン サブスクリプションが無効になります。 テナントからドメインが削除されず、ドメイン上の既存のユーザーやメールボックスには影響しません。

> [!NOTE]
> 購入Microsoft 365ドメインは、ネームサーバーの変更やMicrosoft 365組織間でのドメインの転送の対象になりません。 これらのいずれかが必要な場合は、ドメイン登録を別のレジストラーに転送する必要があります。
