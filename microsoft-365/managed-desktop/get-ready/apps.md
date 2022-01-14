---
title: Microsoft マネージド デスクトップのアプリ
description: アプリのパッケージ化、展開、サポート方法など、アプリの処理方法について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: c53d6c03855da15e71d7d62ec6c26533e0a0db6e
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035608"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのアプリ

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>一般にアプリ

Microsoft には、Microsoft 管理デスクトップに参加するために必要Microsoft 365 E3 E5 ライセンスと共に、特定の主要なアプリが含まれています。 ただし、これらのアプリを提供する場合でも、実行する一定の責任とアクションがあります。

また、ポータル サイト Microsoft Intune または必要なバックグラウンド インストールを通じて、ポータル サイト の展開パイプラインを使用して、ユーザーに追加の Microsoft 以外のアプリを展開することもできます。 

## <a name="apps-provided-by-microsoft"></a>Microsoft が提供するアプリ

Microsoft Managed Desktop ライセンスには、Microsoft 365 Apps for enterprise Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Teams、および OneNote の 64 ビット バージョンのアプリが含まれています。.)クイック実行のMicrosoft ProjectおよびVisioは既定では含まれませんが、追加を要求できます。  これらのアプリの詳細については、「Install Microsoft Project または Microsoft Visio Microsoft Managed Desktop デバイス」[を参照してください](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft が提供するアプリをサポートするために行う機能

Microsoft は、付属のアプリの展開、更新、およびサポートのためのフル サービスMicrosoft 365 Apps for enterpriseします。 クイック実行 Microsoft Project と Visio のバージョンは既定では含まれていませんが、Microsoft Managed Desktop には展開グループが提供され、IT 管理者はライセンスを管理し、組織に合わせてこれらのアプリケーションを適切に展開できます。 Microsoft は、Microsoft Managed Desktop サポート チャネルを通じてこれらのアプリケーションのユーザーをサポートします。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>提供するアプリをサポートするために必要な操作

これらのアプリで行う必要がある特定の操作がまだ存在します。

- **ライセンスの割り** 当て - ユーザーに適切なライセンスを取得し、ユーザーに割り当てるMicrosoft 365 Apps for enterprise。
- **セキュリティ グループにユーザー** を追加する - Microsoft Project または Visioを使用している場合、IT 管理者はそれらのユーザーを適切な展開グループに追加する必要があります。 IT 管理者は、会社を離れた場合にそれらのユーザーからライセンスを再利用する責任も負います。
- **[Microsoft 365 アドオン** を展開する - Microsoft 365 Apps for enterprise アプリのアドオンが必要な場合は、他の Windows 32 アプリと同様に一Windows展開します。 

## <a name="apps-you-provide"></a>提供するアプリ

ビジネス操作に必要な他のアプリがある可能性があります。 これらのアプリは、Microsoft Managed Desktop デバイスにのみ展開できます。このアプリは、Microsoft Intune展開パイプラインを使用します。 アプリケーションの展開の詳細については、「アプリを Microsoft Managed Desktop デバイスに展開 [する」の手順に従います](../get-started/deploy-apps.md)。

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop に含める独自のアプリを準備する
アプリを確認し、次のチェックを行います。

- Microsoft [Managed Desktop](../service-description/mmd-app-requirements.md)アプリの要件で説明されているとおり、禁止または制限された動作を持つアプリはありません。
- アプリは、ユーザーが管理できる状態Microsoft Intune。 このトピックの詳細については、「アプリを使用[Windows 10アプリ](/intune/apps-windows-10-app-deploy)の展開Microsoft Intune」および「アプリの追加」[を参照](/intune/apps-add)Microsoft Intune。
- ライセンス キーの提供、ライセンス条項との契約、サーバー接続の事前設定など、その他の事前パッケージ化要件。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備をする手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. アプリを準備する (この記事)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
