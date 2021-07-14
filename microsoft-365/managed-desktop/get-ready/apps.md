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
ms.openlocfilehash: 37f533f34753d66d975cb557239b2b168ac78f8e
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430770"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのアプリ

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>一般にアプリ

Microsoft には、特定の主要なアプリと、Microsoft 365 E3または E5 ライセンスが含Microsoft マネージド デスクトップ。 ただし、これらのアプリを提供する場合でも、実行する一定の責任とアクションがあります。

また、ポータル サイト Microsoft Intune または必要なバックグラウンド インストールを通じて、ポータル サイト の展開パイプラインを使用して、ユーザーに追加の Microsoft 以外のアプリを展開することもできます。 

## <a name="apps-provided-by-microsoft"></a>Microsoft が提供するアプリ

Microsoft マネージド デスクトップ ライセンスには、Microsoft 365 Apps for enterprise Standard Suite の 64 ビット バージョンのアプリ (Word、Excel、PowerPoint、PowerPoint、Outlook、Publisher、Access、Teams、OneNote) が含まれています。クイック実行のMicrosoft ProjectおよびVisioは既定では含まれませんが、追加を要求できます。  これらのアプリの詳細については、「デバイスにインストールMicrosoft Project[または Microsoft Visio」をMicrosoft マネージド デスクトップしてください](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft が提供するアプリをサポートするために行う機能

Microsoft は、付属のアプリの展開、更新、およびサポートのためのフル サービスMicrosoft 365 Apps for enterpriseします。 クイック実行 Microsoft Project と Visio のバージョンは既定では含まれていませんが、Microsoft マネージド デスクトップ には展開グループが提供され、IT 管理者はライセンスを管理し、組織に合わせてこれらのアプリケーションを適切に展開できます。 Microsoft は、これらのアプリケーションのユーザーをサポートチャネルを通Microsoft マネージド デスクトップサポートします。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>提供するアプリをサポートするために必要な操作

これらのアプリで行う必要がある特定の操作がまだ存在します。

- **ライセンスの割り** 当て - ユーザーに適切なライセンスを取得し、ユーザーに割り当てるMicrosoft 365 Apps for enterprise。
- **セキュリティ グループにユーザー** を追加する - Microsoft Project または Visioを使用している場合、IT 管理者はそれらのユーザーを適切な展開グループに追加する必要があります。 IT 管理者は、会社を離れた場合にそれらのユーザーからライセンスを再利用する責任も負います。
- **[Microsoft 365 アドオン** を展開する - Microsoft 365 Apps for enterprise アプリのアドオンが必要な場合は、他の Windows 32 アプリと同様に一Windows展開します。 

## <a name="apps-you-provide"></a>提供するアプリ

ビジネス操作に必要な他のアプリがある可能性があります。 これらのアプリは、アプリの展開パイプラインMicrosoft マネージド デスクトップ使用して、Microsoft Intuneデバイスにのみ展開できます。 アプリケーションの展開の詳細については、「アプリをデバイスに展開する」[のMicrosoft マネージド デスクトップします](../get-started/deploy-apps.md)。

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>アプリに含める独自のアプリを準備Microsoft マネージド デスクトップ
アプリを確認し、次のチェックを行います。

- 「アプリの要件」で説明されているとおり、どのアプリも禁止または制限[Microsoft マネージド デスクトップはありません](../service-description/mmd-app-requirements.md)。
- アプリは、ユーザーが管理できる状態Microsoft Intune。 このトピックの詳細については、「アプリを使用[Windows 10アプリ](/intune/apps-windows-10-app-deploy)の展開Microsoft Intune」および「アプリの追加」[を参照](/intune/apps-add)Microsoft Intune。
- ライセンス キーの提供、ライセンス条項との契約、サーバー接続の事前設定など、その他の事前パッケージ化要件。

## <a name="steps-to-get-ready"></a>準備の手順

1. 詳細については[、「前提条件」をMicrosoft マネージド デスクトップ。](prerequisites.md)
2. 準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。
3. [ゲスト アカウントの前提条件](guest-accounts.md)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソース アクセスを準備する](authentication.md)
7. [アプリのMicrosoft マネージド デスクトップ](apps.md)(この記事)
8. [Microsoft マネージド デスクトップ用に、マップされたドライブを準備する](mapped-drives.md)
9. [Microsoft マネージド デスクトップ用に、印刷リソースを準備する](printing.md)
