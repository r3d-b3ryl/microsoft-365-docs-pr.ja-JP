---
title: Google Workspace から一般法人向け Microsoft 365 に切り替える
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: データとユーザーを Google Workspace から一般法人向け Microsoft 365 に移動する方法について説明します。
ms.openlocfilehash: 7e469d9cfe8fb5dd8a995050270197cd38fa7e6a
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67087399"
---
# <a name="switch-from-google-workspace---overview"></a>Google Workspace からの切り替え - 概要

次の手順を使用して、データ、メール、ユーザーを Google Workspace から一般法人向け Microsoft 365 に移動できます。 各手順の記事とビデオを使用して、移行する環境を準備および構成し、Microsoft 管理センターで入手可能な移行ツールを使用できるようにします。


| 手順  |説明  |
|---------|---------|
|手順 1 | Microsoft 365 Business Premium に[サインアップ](../admin-overview/sign-up-for-office-365.md)します       |
|手順 2 | [Google Workspace 移行の Microsoft 365 を設定します](set-up-microsoft-365-forgoogle.md)。 </br> この手順では、Google Workspace で使用するドメインを所有していることを確認し、ユーザーを追加し、デバイスの基本的なセキュリティを設定します。 |
|手順 3 | [Windows デバイスのセキュリティ ポリシーを設定します。](../setup/secure-win-10-pcs.md)</br> Windows セキュリティは、Microsoft 365 管理センターの [セットアップ] ページで個別に設定されます。 |
|手順 4 | [Google Workspace ドメインを Microsoft 365 に追加します](add-google-domain.md) </br> メールに使用しているドメインを所有していることを確認した後、自分と他のすべてのユーザーが古いメールを使用して Microsoft 365 Business Premium にサインインできるようになります。 |
|手順 5 | [Office アプリと Microsoft Teams をインストールします](../setup/install-applications.md)。</br> Microsoft 365 ライセンスを持つすべてのユーザーは、職場のデバイスに Office アプリをインストールする必要があります。|
|手順 6 | [すべてのユーザーのメールと予定表アイテムを移行します](migrate-email.md)。</br> この手順では、Google Workspace からすべてのユーザーのメール、予定表、連絡先を移動するために Exchange Online の移行を実行します。  |
|手順 7 | [ドメインを Microsoft 365 に接続します](connect-domain-tom365.md)。 </br> 接続すると、ドメインメールが Microsoft 365 に移動し始め、すべてのMicrosoft 365 サービスが機能します。|
|手順 8|ドライブから OneDrive に、 共有ドライブからチーム サイトに、[すべてのユーザーのデータを移動するために移行マネージャー](migrate-files-migration-manager.md)を使用します。</br> この手順では、個人用ドライブと共有ドライブ内のすべてのデータがコピーされ、Microsoft 365 に移動されます。|
|手順 9| [Google Workspace を停止します](cancel-google.md)が、ドメインは保持します。 </br> Google がドメインを管理している場合は、Google Workspace サブスクリプションを停止した後でも、ドメインを保持できます。 必要に応じて、別の DNS ホストに移動させることもできます。|

