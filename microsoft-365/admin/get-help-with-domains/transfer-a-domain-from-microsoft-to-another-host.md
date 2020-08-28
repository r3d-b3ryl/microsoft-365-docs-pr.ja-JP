---
title: Microsoft から別のホストにドメインを移行する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'この記事では、Microsoft から別のレジストラーにドメインを移行するための手順について説明します。 '
ms.openlocfilehash: c5c1e98ed14c3ac975e55aadbff65e52165a6f8b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289173"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Microsoft から別のホストにドメインを移行する

Microsoft からドメインを購入した後、Microsoft 365 ドメインを別60のレジストラーに移行することはできません。

> [!NOTE]
> _Whois_   クエリは、Microsoft が購入したドメインレジストラーを「ワイルド (_ West Domains) ドメイン」として示しています。 ただし、microsoft 365 の購入済みドメインについては、Microsoft のみに連絡する必要があります。

Microsoft 365 でコードを取得するには、次の手順に従います。その後、他のドメインレジストラー web サイトに移動して、ドメイン名を新しいレジストラーに転送するように設定します。

## <a name="transfer-a-domain"></a>ドメインを転送する

1. 管理センターで、[  **設定**] [ドメイン] に移動し   >  **Domains**ます。

2. [ **ドメイン** ] ページで、別のドメインレジストラーに移行する Microsoft 365 ドメインを選択し、[状態の **確認**] を選択します。

3. ページの上部で、[ドメインの **移行**] を選択します。

4. [ **ドメインを移行する場所を選択** してください] ページで、別の **レジストラー**を選択し、[ **次へ**] をクリックします。

5. [**ドメイン転送のロック解除**] ページで、[ **_ドメイン_ > <の転送のロック解除**] を選択し、[**次へ**] を選択します。

6. ドメイン転送の連絡先情報を確認し、[ **次へ**] を選択します。

7. 次の手順に進む前に、承認コードをコピーして、[**登録**] タブで**転送のロックが解除**されたことを示す30分間待機します。

8. ドメイン名を今後も管理するドメインレジストラーの web サイトに移動します。 ドメインを転送する手順に従います (web サイトでヘルプを検索)。

[認証コードの **登録** ] タブは、Microsoft 365 の [  **ドメイン** ] ページで確認できます。

9. 移行の完了後は、新しいドメイン レジストラーでドメインの更新を実行します。

10. プロセスを終了するには、管理センターの [ **ドメイン** ] ページに戻り、[  **完全なドメイン転送**] を選択します。

> [!NOTE]
> Microsoft 365 で購入したドメインは、ネームサーバーの変更、または Microsoft 365 組織間でのドメインの転送には適していません。 これらのどちらかが必要な場合は、ドメイン登録を別のレジストラーに転送する必要があります。
