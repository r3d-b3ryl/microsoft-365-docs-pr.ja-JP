---
title: Microsoft マネージド デスクトップのアプリ
description: アプリのパッケージ化、展開、サポートの方法など、アプリの処理方法について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 20d68ec007ccda82816ad2288428016019f6d4b2
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840695"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのアプリ

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>一般的なアプリ

Microsoft には、Microsoft マネージド デスクトップへの参加に必要な Microsoft 365 E3 または E5 ライセンスと共に、特定の主要なアプリが含まれています。 ただし、これらのアプリが提供されている場合でも、お客様には完了する特定の責任とアクションがあります。

また、Microsoft Intune の展開パイプラインを使用して、セルフサービス用の追加の Microsoft 以外のアプリをユーザーに展開したり、必要なバックグラウンド インストールを使用したりすることもできます。 専門知識を持っている場合は、自分で必要なアプリを移行できます。または、Microsoft コンサルティング サービス (MCS) または Microsoft 以外のベンダーが、パッケージ化と移行プロジェクトを支援します。 MCS の操作の詳細については、「Microsoft Consulting Services を使用する [」を参照してください](apps-MCS.md)。


## <a name="apps-provided-by-microsoft"></a>Microsoft が提供するアプリ

Microsoft マネージド デスクトップ ライセンスには、Microsoft 365 Apps for enterprise Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote) の 64 ビット バージョンのアプリが含まれています。Microsoft Project および Visio のクリック実行バージョンは既定では含まれていませんが、追加を要求できます。 これらのアプリの詳細については、「Microsoft マネージ デスクトップ デバイスへの [Microsoft Project または Microsoft Visio のインストール」を参照してください](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft が提供するアプリをサポートするために行う機能

Microsoft は、付属の Microsoft 365 Apps for enterprise アプリの展開、更新、サポートに関する完全なサービスを提供します。 既定では、Microsoft Project および Visio のClick-to-Run バージョンは含まれていませんが、Microsoft マネージド デスクトップには展開グループが提供され、IT 管理者はライセンスを管理し、これらのアプリケーションを組織に適した方法で展開できます。 Microsoft は、Microsoft マネージド デスクトップ のサポート チャネルを通じて、これらのアプリケーションのユーザーをサポートします。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>提供するアプリをサポートするために必要な操作

これらのアプリで行う必要のある特定の操作がまだ存在します。

- **ライセンスの割** り当て - Microsoft 365 Apps for enterprise のユーザーに適切なライセンスを取得して割り当てる責任があります。
- **セキュリティ グループに** ユーザーを追加する - Microsoft Project または Visio を使用している場合、IT 管理者はそれらのユーザーを適切な展開グループに追加する必要があります。 IT 管理者は、離社したユーザーからライセンスを解放する責任も負います。
- **Microsoft 365** アドオンの展開 - Microsoft 365 Apps for enterprise アプリのアドオンが必要な場合は、他の Windows 32 アプリと同じ方法で一中心に展開します。 

## <a name="apps-you-provide"></a>提供するアプリ

業務に必要な他のアプリがある可能性があります。 これらのアプリは、Microsoft Intune の展開パイプラインを使用して、Microsoft マネージド デスクトップ デバイスにのみ展開できます。 アプリに必要な場合は、ベンダー (Microsoft 以外のベンダーまたは Microsoft Consulting Services (MCS) の可能性があります) によってパッケージ化するか、または手段がある場合は、自分でパッケージ化することができます。 次に、これらのパッケージを Microsoft マネージド デスクトップ ポータルに追加し、Azure Active Directory グループに割り当て、展開をトリガーします。 

現在 Microsoft Endpoint Configuration Manager を使用してアプリを展開している場合、Microsoft マネージド デスクトップでは、アプリを評価し、Microsoft Intune に移行する準備ができているアプリと調整が必要なアプリを検出するためのクエリを提供できます。


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップに含める独自のアプリの準備
アプリを確認し、次のチェックを行います。

- Microsoft マネージド デスクトップ アプリの要件に記載されているとおり、どのアプリも禁止も動作 [も制限されません](https://aka.ms/app-req)。
- アプリは、Microsoft Intune による管理の準備ができている必要があります。 このトピックの詳細については、「Microsoft Intune を使用した [Windows 10 アプリ](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) の展開」と「Microsoft Intune にアプリを追加する」を [参照してください](https://docs.microsoft.com/intune/apps-add)。
- ライセンス キーの提供、ライセンス条項との合意、サーバー接続の事前設定など、パッケージ化前のその他の要件。

### <a name="decide-how-to-package-apps"></a>アプリをパッケージ化する方法を決定する

一部の独立系ソフトウェア発行元では、アプリを一元的に展開する前にパッケージ化する必要があります。 "パッケージ化" とは、アプリをバックグラウンドでインストールできるよう、ライセンス キー、リモート サーバーの場所、デスクトップ ショートカットのような設定でアプリのインストーラーが構成されていることを意味します。

アプリをパッケージ化するには、次の 3 つのオプションがあります。 


- 自分でアプリをパッケージ化できます
- Microsoft 以外のベンダーと一緒に作業できます
- MCS を使ってアプリをパッケージ化できます。 Microsoft アカウントの担当者と一緒に作業します。 詳細については [、「Microsoft Consulting Services の使用」を参照してください](apps-MCS.md)。



## <a name="deploying-apps"></a>アプリの展開

アプリのパッケージ化に使用する方法は何でも、完了したら、「Microsoft マネージド デスクトップ デバイスにアプリを展開する」の手順 [に従う準備が整います](../get-started/deploy-apps.md)。


