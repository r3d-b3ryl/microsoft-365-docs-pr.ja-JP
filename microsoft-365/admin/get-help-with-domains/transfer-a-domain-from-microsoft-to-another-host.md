---
title: Microsoft から別のホストにドメインを転送する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 'ドメインを Microsoft から別のレジストラーに転送するには、以下の手順を実行します。 '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126349"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Microsoft から別のホストにドメインを転送する

Microsoft からドメインを購入した後、60 日間、Microsoft 365 ドメインを別のレジストラーに転送できない。

> [!NOTE]
> _Whois クエリは_   、Microsoft が購入したドメイン レジストラーを Wild West Domains LLC として表示します。 ただし、Microsoft 365 購入ドメインに関して Microsoft にのみ連絡する必要があります。

次の手順に従って Microsoft 365 でコードを取得し、他のドメイン レジストラー Web サイトに移動して、ドメイン名を新しいレジストラーに転送する設定を行います。

## <a name="transfer-a-domain"></a>ドメインを転送する

1. 管理センターで、[設定ドメイン]  **に**   >  **移動します**。

2. [ **ドメイン] ページ** で、別のドメイン レジストラーに転送する Microsoft 365 ドメインを選択し、[正常性の確認] を **選択します**。

3. ページの上部で、[ドメインの転送] **を選択します**。

4. On the **Choose where to transfer your domain** page, select A different **registrar,** and then click **Next**.

5. On the **Unlock domain transfer** page, select Unlock transfer for <your **_domain,_ >** and then select **Next**.

6. ドメイン転送の連絡先情報を確認し、[次へ] を選択 **します**。

7. 次の手順に進む前に、認証コードをコピーして、ドメインの転送状態が [登録]タブの [ロック解除済み] に変わるまで約 30 分待ちます。

8. 今後ドメイン名を管理するドメイン レジストラーの Web サイトに移動します。 ドメインを転送するための指示に従います (Web サイトでヘルプを検索してください)。 これは通常、転送料金を支払い、新しいレジストラーに認証コードを提供して、転送を開始できるという意味です。 Microsoft から転送要求を受け取ったことを確認するメールが送信され、ドメインは 5 日以内に転送されます。

    認証コードの登録タブは、Microsoft 365 の [ドメイン] ページにあります。  ****
    
    > [!TIP]
    > .uk ドメインには別の手順が必要です。 Microsoft サポートに連絡して、今後ドメインを管理するレジストラーと一致するように **IPS Tag タグを変更** を依頼します。 タグを変更すると、ドメインは直ちに新しいレジストラーに移動します。 転送を完了するには、新しいレジストラーでするべきことがあります。移転手数料を支払って、新しいレジストラーで転送されたドメインをアカウントに追加する必要があります。

9. 移行の完了後は、新しいドメイン レジストラーでドメインの更新を実行します。

10. プロセスを完了するには、管理センターの [ **ドメイン** ] ページに戻り、[ドメインの転送の完了]  **を選択します**。 これにより、ドメインが Microsoft 365 から購入されなくなったとマークされ、ドメイン サブスクリプションが無効にされます。 テナントからドメインは削除されません。また、ドメイン上の既存のユーザーとメールボックスには影響を与えされません。

> [!NOTE]
> Microsoft 365 購入ドメインは、ネームサーバーの変更または Microsoft 365 組織間でのドメインの転送の対象ではありません。 これらのどちらかが必要な場合は、ドメイン登録を別のレジストラーに転送する必要があります。
