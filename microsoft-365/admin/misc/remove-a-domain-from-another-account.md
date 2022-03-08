---
title: 別のアカウントからドメインを削除する
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: セルフサービス ユーザーサインアップによって作成されたアンマネージ アカウントに参加する方法については、Microsoft 365。
ms.openlocfilehash: 0a7cf07a70e241c0b40f28159f31b0c86766bc1d
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325671"
---
# <a name="perform-an-internal-admin-takeover"></a>内部管理者の引き取りを実行する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

管理者であり、セルフサービス ユーザーサインアップによって作成された管理されていないアカウントを引き継ぐ場合は、内部管理者の引き継ぎを実行してこれを行います。

> [!NOTE]
> セルフサービスは、Azure AD を使用するクラウド サービスにサインアップし、ユーザーを管理されていないディレクトリまたは "シャドウ" Azure AD ディレクトリに追加し、管理されていないアカウントを作成します。 管理されていないアカウントは、グローバル管理者のないディレクトリです。 アカウントが管理されているかどうかを確認するには、「テナントの種類の決定 [」を参照してください](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="before-you-begin"></a>始める前に

そのドメイン名に関連付けられた電子メール アドレスを使用して、他のユーザーが既に Microsoft 365アカウントにドメインを追加できない場合があります。 ただし、他の管理されていないアカウントからドメインを削除し、組織の管理アカウントに追加できます。

ドメインを他のアカウントから削除してアカウントに追加する前に、アンマネージ アカウントに参加し、そのアカウントの管理者になる必要があります。 次に、管理されていないアカウントからドメインを削除し、アカウントにサインインし、そのドメインを管理アカウントに追加します。

この記事の手順では、他のアカウントに参加する方法 (手順 1 と手順 2) のみを概説し、管理者の引き継ぎウィザードの手順に従って、管理されていないアカウントの管理者になります (手順 3)。

管理されていないアカウントの管理者になったら、管理されていないアカウントからドメインを削除し、アカウントに追加できます。 

## <a name="step-1-verify-your-email-address"></a>手順 1: メール アドレスを確認する

> [!NOTE]
> アカウントでセルフサービスが有効になっている場合、ユーザーは自分で無料サービス (Power BIなど) を購読できます。 これらのサービスは、セルフサービス ユーザー サブスクリプションが管理者として引き継ぐアンマネージ アカウントを作成した場合に特に使用されます。手順 1 では、Power BI を使用して管理用の引き継ぎウィザードを起動して、削除するドメインのユーザー アカウントを作成し、管理されていないドメイン アカウントの管理者になれ。

1. アプリにサインアップするには、Power BI サイトに移動し、[無料の無料試用版 [のPower BI](https://powerbi.com) > **する] (**[無料の試用版と共有する] ボックス) をPower BI Proします。 

2. 組織のドメイン名 (など) を使用するユーザー アカウントにサインアップします `powerbiadmin@contoso.com`。 アカウントが既に使用されている場合は、現在のパスワードを使用してサインインします。

3. 確認コードをメールで確認 **し、** メール アドレスを検証するコードを入力します。

## <a name="step-2-create-a-new-account-for-admin-access"></a>手順 2: 管理者アクセス用の新しいアカウントを作成する

1. 確認コードを入力すると、新しいアカウントを作成できるページに移動します。

2. 使用するアカウントでユーザー名とパスワードフィールドを入力し、[スタート] を選択 **します**。

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>手順 3: ドメインの所有権を確認し、管理者になる

1. 手順 2 を完了したら、左側のナビゲーション ウィンドウで管理センター アイコンを選択します (または、ブラウザーに移動して入力します `https://admin.microsoft.com`)。

    管理者の引き取りウィザードにリダイレクトされます。

1. [ **次へ** ] を選択し、ドメイン レジストラーに TXT レコードを追加して、引き継ぐドメインを所有している必要があります。 

    ウィザードは、追加する TXT レコードを提供し、レジストラーの Web サイトへのリンクと、詳細な手順へのリンクを提供します。

1. [管理 **] ページで、[** 管理センターに移動] **を選択します**。

    これで、他のアカウントからドメインを削除するために必要な管理者権限が付与されます。 
## <a name="related-content"></a>関連コンテンツ

YouTube: [IT](https://www.youtube.com/watch?v=xt5EsrQBZZk) 管理者の引き取りを行う 3 つのPower BIとMicrosoft 365 (ビデオ)\
[管理者の引きAzure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (記事)\
[組織でセルフサービス サインアップを使用](self-service-sign-up.md) する (記事)\
[サービス管理者Power BIロールについて](/power-bi/service-admin-role) (記事)
