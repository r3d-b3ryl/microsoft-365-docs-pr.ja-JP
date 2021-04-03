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
ms.openlocfilehash: d970ac1a28c62703f648e4fbf6f66e2f825a6188
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574621"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのアプリ

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>一般にアプリ

Microsoft には、Microsoft Managed Desktop への参加に必要な Microsoft 365 E3 または E5 ライセンスと共に、特定の主要アプリが含まれています。 ただし、これらのアプリを提供する場合でも、実行する一定の責任とアクションがあります。

また、Microsoft Intune の展開パイプラインを使用して、追加の Microsoft 以外のアプリをセルフサービス用にユーザーに展開したり、必要なバックグラウンド インストールを実行したりすることもできます。 専門知識を持っている場合は、自分で必要なアプリを移行できます。または、Microsoft コンサルティング サービス (MCS) または Microsoft 以外のベンダーが、パッケージ化と移行プロジェクトを支援します。 MCS の操作の詳細については、「Microsoft コンサルティング サービスの使用 [」を参照してください](apps-MCS.md)。


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

ビジネス操作に必要な他のアプリがある可能性があります。 これらのアプリは、Microsoft Intune の展開パイプラインを使用して Microsoft Managed Desktop デバイスにのみ展開できます。 アプリが必要とする場合は、ベンダー (Microsoft 以外のベンダーまたは Microsoft コンサルティング サービス (MCS) の場合) によってパッケージ化するか、手段がある場合は、自分でパッケージ化できます。 次に、これらのパッケージを Microsoft Managed Desktop ポータルに追加し、それらを Azure Active Directory グループに割り当て、展開をトリガーします。 

現在、Microsoft Endpoint Configuration Manager を使用してアプリを展開している場合、Microsoft Managed Desktop は、アプリを評価し、Microsoft Intune に移行する準備ができているアプリと、調整が必要になる可能性のあるアプリを検出するためのクエリを提供できます。


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop に含める独自のアプリを準備する
アプリを確認し、次のチェックを行います。

- Microsoft [Managed Desktop](../service-description/mmd-app-requirements.md)アプリの要件で説明されているとおり、禁止または制限された動作を持つアプリはありません。
- アプリは、Microsoft Intune による管理の準備ができている必要があります。 このトピックの詳細については、「Microsoft Intune を使用した [Windows 10 アプリ](/intune/apps-windows-10-app-deploy) の展開」および「Microsoft Intune にアプリを追加する」 [を参照してください](/intune/apps-add)。
- ライセンス キーの提供、ライセンス条項との契約、サーバー接続の事前設定など、その他の事前パッケージ化要件。

### <a name="decide-how-to-package-apps"></a>アプリをパッケージ化する方法を決定する

独立したソフトウェア発行元によっては、アプリを一元的に展開する前にパッケージ化する必要がある場合があります。 "パッケージ化" とは、アプリをバックグラウンドでインストールできるよう、アプリのインストーラーがライセンス キー、リモート サーバーの場所、デスクトップ ショートカットのような設定で構成されていることを意味します。

アプリをパッケージ化するには、次の 3 つのオプションがあります。 


- 自分でアプリをパッケージ化できます
- Microsoft 以外のベンダーと作業できます
- MCS に参加してアプリをパッケージ化できます。 Microsoft アカウント担当者と一緒に作業します。 詳細については [、「Microsoft コンサルティング サービスの操作」を参照してください](apps-MCS.md)。



## <a name="deploying-apps"></a>アプリの展開

アプリをパッケージ化するために使用する方法が何であれ、完了したら、「アプリを Microsoft Managed Desktop デバイスに展開する」の手順に従 [う準備ができました](../get-started/deploy-apps.md)。


## <a name="steps-to-get-ready"></a>準備の手順

1. 「Microsoft [Managed Desktop の前提条件」を参照してください](prerequisites.md)。
2. 準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。
3. [ゲスト アカウントの前提条件](guest-accounts.md)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する](authentication.md)
7. [Microsoft Managed Desktop のアプリ](apps.md) (この記事)
8. [Microsoft マネージド デスクトップ用に、マップされたドライブを準備する](mapped-drives.md)
9. [Microsoft マネージド デスクトップ用に、印刷リソースを準備する](printing.md)
