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
ms.openlocfilehash: ce43080c284c4c15be5a8799f70a43de611ff9ba
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520441"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのアプリ

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->

## <a name="apps-generally"></a>一般にアプリ

Microsoft には、Microsoft 管理デスクトップに参加するために必要Microsoft 365 E3 E5 ライセンスと共に、特定の主要なアプリが含まれています。 ただし、これらのアプリを提供する場合でも、実行する一定の責任とアクションがあります。

また、ポータル サイト を介してセルフサービスを介して追加の Microsoft 以外のアプリをユーザーに展開したり、Microsoft Intune の展開パイプラインを使用して必要なバックグラウンド インストールを展開することもできます。

## <a name="apps-provided-by-microsoft"></a>Microsoft が提供するアプリ

Microsoft Managed Desktop ライセンスに含まれるアプリは、Microsoft 365 Apps for Enterprise Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Teams、およびOneNote.)

クイック実行のMicrosoft ProjectとVisioは既定では含まれませんが、追加を要求できます。 これらのアプリの詳細については、「Install [Microsoft Projectまたは Microsoft Visio デスクトップ デバイス」を参照してください](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft が提供するアプリをサポートするために行う機能

Microsoft は、付属のアプリの展開、更新、およびサポートのためのフル サービスMicrosoft 365 Apps for enterpriseします。 クイック実行とMicrosoft ProjectのVisio *は既定では* 含まれません。 ただし、Microsoft Managed Desktop には、IT 管理者がライセンスを管理し、組織に合わせて適切にこれらのアプリケーションを展開するための展開グループが提供されます。 Microsoft は、Microsoft Managed Desktop サポート チャネルを通じてこれらのアプリケーションのユーザーをサポートします。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>提供するアプリをサポートするために必要な操作

これらのアプリで行う必要がある特定の操作がまだ存在します。

| タスク | 説明 |
| ------ | ------ |
| ライセンスの割り当て | ユーザーに対して適切なライセンスを取得し、割り当てる責任Microsoft 365 Apps for enterprise。 |
| セキュリティ グループにユーザーを追加する | 管理者または管理者をMicrosoft Project場合Visio、IT 管理者はそれらのユーザーを適切な展開グループに追加する必要があります。 IT 管理者は、会社を離れた場合にそれらのユーザーからライセンスを再利用する責任も負います。 |
| アドオンMicrosoft 365展開する | 任意のアプリにアドオンが必要な場合は、Microsoft 365 Apps for enterprise 32 アプリと同様に一Windows展開します。

## <a name="apps-you-provide"></a>提供するアプリ

ビジネス操作に必要な他のアプリがある可能性があります。 これらのアプリは、Microsoft Managed Desktop デバイスにのみ展開できます。このアプリは、Microsoft Intune展開パイプラインを使用します。 アプリケーションの展開の詳細については、「 [アプリを Microsoft Managed Desktop デバイスに展開する」の手順に従います](../get-started/deploy-apps.md)。

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop に含める独自のアプリを準備する

アプリを確認し、次のチェックを行います。

- Microsoft [Managed Desktop](../service-description/mmd-app-requirements.md) アプリの要件で説明されているとおり、禁止または制限された動作を持つアプリはありません。
- アプリは、ユーザーが管理できる状態Microsoft Intune。 詳細については、「アプリを使用[Windows 10アプリ](/intune/apps-windows-10-app-deploy)の展開Microsoft Intuneアプリを追加する[」を参照](/intune/apps-add)Microsoft Intune。
- ライセンス キーの提供、ライセンス条項との契約、サーバー接続の事前設定など、その他の事前パッケージ化要件。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備をする手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
1. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. アプリを準備する (この記事)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
