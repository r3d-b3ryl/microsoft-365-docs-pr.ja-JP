---
title: Microsoft マネージドデスクトップのアプリ
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: adb6423d5c014b5f02fc272f9653abebc14cf543
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557575"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップのアプリ

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>通常、アプリ

Microsoft では、microsoft マネージドデスクトップに参加するために必要な Microsoft 365 E3 または E5 ライセンスと共に、特定の主要なアプリが含まれています。 ただし、これらのアプリが提供されている場合でも、一部の責任とアクションを完了することができます。

また、Microsoft Intune の展開パイプラインを使用して、会社のポータルまたは必要なバックグラウンドインストールを通じて、Microsoft 以外の追加のアプリをエンドユーザーに展開することもできます。 専門知識を持っている場合は、必要なアプリを自分で移行できます。または、Microsoft コンサルティングサービス (MCS) または Microsoft 以外のベンダーが、パッケージ化と移行のプロジェクトにお役立てください。 MCS の使用の詳細については、「 [Microsoft コンサルティングサービスを使用](apps-MCS.md)する」を参照してください。


## <a name="apps-provided-by-microsoft"></a>Microsoft によって提供されるアプリ

Microsoft Managed Desktop license には、Office 365 ProPlus Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、および OneNote) のアプリの64ビットバージョンが含まれています。クイック実行バージョンの Microsoft Project と Visio は既定では含まれて*いません*が、追加するように要求することができます。 これらのアプリの詳細については、「microsoft [Project または Microsoft Visio を Microsoft マネージドデスクトップデバイスにインストール](../get-started/project-visio.md)する」を参照してください。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft が提供するアプリのサポート内容

Microsoft は、含まれている Office 365 ProPlus アプリの展開、更新、およびサポートに対して完全なサービスを提供します。 既定では、クイック実行バージョンの Microsoft Project と Visio は含まれて*いません*が、Microsoft Managed Desktop は展開グループを提供し、IT 管理者がライセンスを管理したり、組織に適したアプリケーションを展開したりできるようにします。 Microsoft は、Microsoft マネージドデスクトップサポートチャネルを使用して、これらのアプリケーションのエンドユーザーをサポートします。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>提供するアプリをサポートするために必要な作業

これらのアプリで実行する必要があるいくつかの事柄があります。

- **ライセンスの割り当て**-Office 365 ProPlus のエンドユーザーに対して適切なライセンスを取得して割り当てる責任があります。
- **セキュリティグループにユーザーを追加する**-Microsoft Project または Visio を使用している場合は、IT 管理者が該当する展開グループにユーザーを追加する必要があります。 IT 管理者は、そのユーザーが会社を去る場合に、そのユーザーからライセンスを再利用する責任も担います。
- **Office 365 アドオンを展開**する-Office 365 ProPlus アプリのいずれかにアドオンが必要な場合は、他の Windows 32 アプリと同じように展開します。 

## <a name="apps-you-provide"></a>提供するアプリ

もちろん、ビジネス運用に必要なその他のアプリが多数存在する可能性があります。 これらは microsoft Intune の展開パイプラインを使用して、Microsoft マネージドデスクトップデバイスにのみ展開できます。 アプリで必要になるのは、ベンダーによってパッケージ化されている場合 (Microsoft 以外のベンダーまたは Microsoft コンサルティングサービス (MCS) である場合もあります)、または手段を持っている場合は自分でパッケージ化することができます。 次に、これらのパッケージを Microsoft マネージドデスクトップポータルに追加して、展開を開始するように Azure Active Directory グループに割り当てます。 

Microsoft エンドポイント構成マネージャーを使用して現在アプリを展開している場合、Microsoft マネージドデスクトップでは、アプリを評価して、Microsoft Intune に移行する準備ができているものと、必要なものがあるかどうかを検出するためのクエリを提供できます。セレクター.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップに含める独自のアプリの準備
アプリを確認し、次の点を確認します。

- 「 [Microsoft Managed Desktop app の要件](https://aka.ms/app-req)」で説明されているように、禁止されている、または制限された動作を持つアプリはありません。
- アプリは、Microsoft Intune による管理の準備が整っている必要があります。 詳細については、「 [Microsoft intune を使用した Windows 10 アプリの展開](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)」および「 [microsoft intune にアプリを追加する](https://docs.microsoft.com/intune/apps-add)」を参照してください。
- ライセンスキーの提供、ライセンス条項に同意する、事前設定のサーバー接続など、その他のプレパッケージング要件。

### <a name="decide-how-to-package-apps"></a>アプリをパッケージ化する方法を決定する

一部の独立系ソフトウェアベンダーは、中央に展開する前に、アプリをパッケージ化する必要がある場合があります。 "パッケージング" とは、アプリのインストーラーが、バックグラウンドでアプリをインストールできるように、ライセンスキー、リモートサーバーの場所、またはデスクトップショートカットなどの設定で構成されることを意味します。

アプリをパッケージ化するには、次の3つのオプションがあります。 


- アプリを自分でパッケージ化することができます。
- Microsoft 以外のベンダーと協力して作業することができます。
- アプリケーションをパッケージ化するために MCS と連携することができます。 Microsoft アカウントの担当者と協力してください。 詳細については、「 [Microsoft コンサルティングサービスを使用](apps-MCS.md)する」を参照してください。







## <a name="deploying-apps"></a>アプリの展開

パッケージをパッケージ化するためにどのような方法を使用する場合でも、「 [Microsoft マネージドデスクトップデバイスへのアプリの展開](../get-started/deploy-apps.md)」の手順を実行する準備ができています。


