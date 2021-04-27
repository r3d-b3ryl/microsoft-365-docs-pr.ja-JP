---
title: Microsoft マネージド デスクトップのアプリ
description: アプリのパッケージ化、展開、サポート方法など、アプリの処理方法について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028946"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのアプリ

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>一般にアプリ

Microsoft には、Microsoft Managed Desktop への参加に必要な Microsoft 365 E3 または E5 ライセンスと共に、特定の主要アプリが含まれています。 ただし、これらのアプリを提供する場合でも、実行する一定の責任とアクションがあります。

また、Microsoft Intune の展開パイプラインを使用して、追加の Microsoft 以外のアプリをセルフサービス用にユーザーに展開したり、必要なバックグラウンド インストールを実行したりすることもできます。 

## <a name="apps-provided-by-microsoft"></a>Microsoft が提供するアプリ

Microsoft Managed Desktop ライセンスには、Microsoft 365 Apps for enterprise Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote) の 64 ビット バージョンのアプリが含まれています。クイック実行バージョンの Microsoft Project と Visioは既定では含まれていませんが、追加を要求できます。 これらのアプリの詳細については、「Microsoft マネージ デスクトップ デバイスに Microsoft Project または Microsoft Visio をインストールする [」を参照してください](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft が提供するアプリをサポートするために行う機能

Microsoft は、付属の Microsoft 365 Apps for enterprise Apps の展開、更新、およびサポートのためのフル サービスを提供します。 クイック実行バージョンの Microsoft Project と Visioは既定では含まれていませんが、Microsoft Managed Desktop には展開グループが提供され、IT 管理者はライセンスを管理し、組織に合わせてこれらのアプリケーションを適切に展開できます。 Microsoft は、Microsoft Managed Desktop サポート チャネルを通じてこれらのアプリケーションのユーザーをサポートします。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>提供するアプリをサポートするために必要な操作

これらのアプリで行う必要がある特定の操作がまだ存在します。

- **ライセンスの割り** 当て - Microsoft 365 Apps for enterprise のユーザーに適切なライセンスを取得して割り当てる責任があります。
- **セキュリティ グループにユーザーを追加** する - Microsoft Project または Visio を使用している場合、IT 管理者はそれらのユーザーを適切な展開グループに追加する必要があります。 IT 管理者は、会社を離れた場合にそれらのユーザーからライセンスを再利用する責任も負います。
- **Microsoft 365** アドオンを展開する - エンタープライズ アプリ用の Microsoft 365 アプリのアドオンが必要な場合は、他の Windows 32 アプリと同様に一中心に展開します。 

## <a name="apps-you-provide"></a>提供するアプリ

ビジネス操作に必要な他のアプリがある可能性があります。 これらのアプリは、Microsoft Intune の展開パイプラインを使用して Microsoft Managed Desktop デバイスにのみ展開できます。 アプリケーションの展開の詳細については、「アプリを Microsoft Managed Desktop デバイスに展開 [する」の手順に従います](../get-started/deploy-apps.md)。

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop に含める独自のアプリを準備する
アプリを確認し、次のチェックを行います。

- Microsoft [Managed Desktop](../service-description/mmd-app-requirements.md)アプリの要件で説明されているとおり、禁止または制限された動作を持つアプリはありません。
- アプリは、Microsoft Intune による管理の準備ができている必要があります。 このトピックの詳細については、「Microsoft Intune を使用した [Windows 10 アプリ](/intune/apps-windows-10-app-deploy) の展開」および「Microsoft Intune にアプリを追加する」 [を参照してください](/intune/apps-add)。
- ライセンス キーの提供、ライセンス条項との契約、サーバー接続の事前設定など、その他の事前パッケージ化要件。

## <a name="steps-to-get-ready"></a>準備の手順

1. 「Microsoft [Managed Desktop の前提条件」を参照してください](prerequisites.md)。
2. 準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。
3. [ゲスト アカウントの前提条件](guest-accounts.md)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソース アクセスを準備する](authentication.md)
7. [Microsoft Managed Desktop のアプリ](apps.md) (この記事)
8. [Microsoft マネージド デスクトップ用に、マップされたドライブを準備する](mapped-drives.md)
9. [Microsoft マネージド デスクトップ用に、印刷リソースを準備する](printing.md)
