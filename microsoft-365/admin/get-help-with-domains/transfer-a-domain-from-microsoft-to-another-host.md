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
description: 'Microsoft から別のレジストラーにドメインを転送する手順については、こちらを参照してください。 '
ms.openlocfilehash: 192e9c1e14666f80fb670c5c8e268ae54ece0c64
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316773"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Microsoft から別のホストにドメインを転送する

Microsoft からドメインを購入した後Microsoft 365ドメインを別のレジストラーに 60 日間転送できない。

> [!NOTE]
> _Whoisquery_  は、Microsoft が購入したドメイン レジストラーをワイルド ウェスト ドメイン LLC として表示します。 ただし、購入したドメインに関して Microsoft Microsoft 365する必要があります。

次の手順に従って、Microsoft 365 でコードを取得し、他のドメイン レジストラー Web サイトに移動して、ドメイン名を新しいレジストラーに転送する設定を行います。

## <a name="transfer-a-domain"></a>ドメインの転送

1. 管理センターで、[ドメイン]   **設定** > **に移動します**。

2. [ドメイン **] ページで**、別のMicrosoft 365に転送するドメインを選択し、[正常性の確認] **を選択します**。

3. ページの上部で、[ドメインの転送] **を選択します**。

4. [ドメインの **転送先の選択] ページで** 、[ **別のレジスト** ラー] を選択し、[次へ] をクリック **します**。

5. [ドメイン転送 **のロック解除] ページ** で、[ドメインの転送のロック<**_]_> を選択し、[次** へ] を選択 **します**。

6. ドメイン転送の連絡先情報を確認し、[次へ] を **選択します**。

7. 認証コードをコピーし、ドメイン転送の状態が [登録] タブの **[転送** のロック解除済み] に変わるまで約 30 分待機してから、次の手順に進みます。

8. 今後ドメイン名を管理するドメイン レジストラーの Web サイトに移動します。 ドメインを転送するための指示に従います (Web サイトでヘルプを検索します)。 これは通常、転送手数料を支払い、新しいレジストラーに Authcode を渡して、転送を開始できるという意味です。 Microsoft から転送要求を受け取ったことを確認するメールが送信され、ドメインは 5 日以内に転送されます。

    認証コードの [登録] タブ **は**、[ドメイン  ****] ページの [Microsoft 365。
    
    > [!TIP]
    > .uk ドメインでは、別の手順が必要です。 Microsoft サポートに連絡して、今後ドメインを管理するレジストラーと一致するように **IPS Tag タグを変更** を依頼します。 タグを変更すると、ドメインは直ちに新しいレジストラーに移動します。 転送を完了するには、新しいレジストラーでするべきことがあります。移転手数料を支払って、新しいレジストラーで転送されたドメインをアカウントに追加する必要があります。

9. 移行の完了後は、新しいドメイン レジストラーでドメインの更新を実行します。

10. プロセスを完了するには、管理センターの **[ドメイン** ] ページに戻り、[  **Complete ドメイン転送] を選択します**。 これにより、ドメインはドメインから購入されなくなったMicrosoft 365し、ドメイン サブスクリプションを無効にします。 テナントからドメインは削除されません。また、ドメイン上の既存のユーザーとメールボックスには影響を与えかねない。

> [!NOTE]
> Microsoft 365したドメインは、ネームサーバーの変更や組織間でのドメインのMicrosoft 365されません。 これらのどちらかが必要な場合は、ドメイン登録を別のレジストラーに転送する必要があります。
