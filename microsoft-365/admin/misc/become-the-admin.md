---
title: 内部管理者の引き取りを実行する
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
description: Microsoft 365 のセルフサービス ユーザー サインアップによって作成された管理されていないアカウントを引き継ぐメールとドメインの所有権を確認する方法について説明します。
ms.openlocfilehash: 06197bb5326cbd19fcd9174554007577e7086dc6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320159"
---
# <a name="perform-an-internal-admin-takeover"></a>内部管理者の引き取りを実行する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

管理者で、セルフサービス ユーザーサインアップによって作成された管理されていないアカウントを引き継ぐ場合は、この記事の手順に従って内部管理者の引き継ぎを実行できます。

> [!NOTE]
> Azure AD を使用するクラウド サービスにセルフサービスサインアップすると、ユーザーは管理されていないまたは "シャドウ" な Azure AD ディレクトリに追加され、管理されていないアカウントが作成されます。 管理されていないアカウントは、グローバル管理者のないディレクトリです。 アカウントが管理されているかどうかを確認するには、「テナントの種類の決定 [」を参照してください](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="before-you-begin"></a>始める前に

ユーザーが電子メール アドレスを使用して Microsoft 365 サービスに登録すると、アカウントが自動的に作成されます。 管理者がアカウントのユーザーを管理したり、追加の Microsoft 365 サービスを購入したりする場合は、管理者の引き取りを実行するには、次の手順に従ってアカウントの管理者になる必要があります。

## <a name="step-1-verify-your-email-address"></a>手順 1: メール アドレスを確認する

> [!NOTE]
> アカウントでセルフサービスが有効になっている場合、ユーザーは Power BI などの無料サービスを自分で購読できます。 これらのサービスは、セルフサービス ユーザー サブスクリプションが管理者として引き継ぐアンマネージ アカウントを作成した場合に特に使用されます。手順 1 では、Power BI を使用して管理用の引き継ぎウィザードを起動して削除するドメインのユーザー アカウントを作成し、管理されていないドメイン アカウントの管理者になれ。

1. Power BI にサインアップするには、[Power BI](https://powerbi.com) サイトに移動し、[**FreeStart** >  無料試用版の開始] ([Power BI Pro と共有] ボックス) を選択します。 

2. 組織のドメイン名 (など) を使用するユーザー アカウントにサインアップします `powerbiadmin@contoso.com`。 アカウントが既に使用されている場合は、現在のパスワードを使用してサインインします。

3. 確認コードをメールで確認 **し、** メール アドレスを検証するコードを入力します。

## <a name="step-2-create-a-new-account-for-admin-access"></a>手順 2: 管理者アクセス用の新しいアカウントを作成する

1. 確認コードを入力すると、新しいアカウントを作成できるページに移動します。

2. ユーザー名とパスワード フィールドに、使用するアカウントを入力し、手順を実行してアカウントを作成します。

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>手順 3: ドメインの所有権を確認し、管理者になる

1. 手順 2 を完了したら、左側のナビゲーション ウィンドウで管理センター アイコンを選択します (または、ブラウザーに移動して入力します `https://admin.microsoft.com`)。

    管理者の引き取りウィザードにリダイレクトされます。

2. [ **次へ** ] を選択し、ドメイン レジストラーに TXT レコードを追加して、引き継ぐドメインを所有している必要があります。

    ウィザードは、追加する TXT レコードを提供し、レジストラーの Web サイトへのリンクと、詳細な手順へのリンクを提供します。

3. [管理 **] ページで、[** 管理センターに移動] **を選択します**。

    管理センターでアカウントを管理するために必要な管理者特権があります。 たとえば、アカウント のユーザーとグループを管理し、新しいサブスクリプションを購入し、ユーザー割り当てを行い、アカウント ドメインを管理できます。

    このアカウントからドメインを削除して別のアカウントに追加する場合は、「別のアカウントからドメインを削除する」 [を参照してください](remove-a-domain-from-another-account.md)。
  
## <a name="related-content"></a>関連コンテンツ

YouTube: [Power BI と Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (ビデオ)の IT 管理者の引き取りを行う 3 つの手順
[Azure での管理者の引き](/azure/active-directory/users-groups-roles/domains-admin-takeover) AD (記事)\
[組織でセルフサービス サインアップを使用](self-service-sign-up.md) する (記事)\
[Power BI Service 管理者の役割について](/power-bi/service-admin-role) (記事)