---
title: 内部管理者の引き継ぎを実行する
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
description: Microsoft 365 でのセルフサービス ユーザーサインアップによって作成されたアンマネージド アカウントを引き継ぐ電子メールとドメインの所有権を確認する方法について説明します。
ms.openlocfilehash: b930e9d4774dc9271d4bcbd93ffb9e5ced577dab
ms.sourcegitcommit: 8a0de6240facfe26ee391a14076b7fe534ee6598
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2022
ms.locfileid: "65922133"
---
# <a name="internal-admin-takeover"></a>内部管理者の引き継ぎ

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

管理者であり、セルフサービス ユーザーサインアップによって作成された管理されていないアカウントを引き継ぐ場合は、この記事の手順に従って内部管理者の引き継ぎを実行できます。

> [!NOTE]
> Azure AD を使用するすべてのクラウド サービスに対するセルフサービス サインアップでは、ユーザーが非管理対象または "シャドウ" の Azure AD ディレクトリに追加され、非管理対象アカウントが作成されます。 アンマネージド アカウントは、グローバル管理者がいないディレクトリです。 アカウントが管理されているか管理されていないかを確認するには、 [テナントの種類の決定に関するページを](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)参照してください。 
  
## <a name="before-you-begin"></a>はじめに

ユーザーが電子メール アドレスを使用して Microsoft 365 サービスにサインアップすると、アカウントが自動的に作成されます。 管理者がアカウントでユーザーを管理する場合、または追加の Microsoft 365 サービスを購入する場合は、管理者の引き継ぎを実行するには、次の手順に従ってアカウントの管理者になる必要があります。

## <a name="step-1-verify-your-email-address"></a>手順 1: メール アドレスを確認する

> [!NOTE]
> アカウントでセルフサービスが有効になっている場合、ユーザーは Power BI などの無料サービスを自分でサブスクライブできます。 これらのサービスは、特に、セルフサービス ユーザー サブスクリプションが管理者として引き継ぐアンマネージド アカウントを作成した場合に使用します。手順 1 では、Power BI を使用して削除するドメインのユーザー アカウントを作成し、管理されていないドメイン アカウントの管理者になるために、管理者の引き継ぎウィザードを起動します。

1. Power BI にサインアップするには、 [Power BI サイト](https://powerbi.com) に移動し、 **無料** > **試用版の開始** ([Power BI Pro と共有] ボックスで) を選択します。 

2. 組織のドメイン名 (など `powerbiadmin@contoso.com`) を使用するユーザー アカウントでサインアップします。 アカウントが既に使用されている場合は、現在のパスワードを使用してサインインします。

3. **確認コード** をメールで確認し、電子メール アドレスを検証するコードを入力します。

## <a name="step-2-create-a-new-account-for-admin-access"></a>手順 2: 管理者アクセス用の新しいアカウントを作成する

1. 確認コードを入力すると、新しいアカウントを作成できるページに移動します。

2. ユーザー名フィールドとパスワード フィールドに使用するアカウントを入力し、アカウントを作成する手順を完了します。

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>手順 3: ドメインの所有権を確認し、管理者になる

1. 手順 2 を完了したら、左側のナビゲーション ウィンドウで管理センター アイコンを選択します (または、ブラウザーに移動して入力 `https://admin.microsoft.com`します)。

    管理者の引き継ぎウィザードにリダイレクトされます。

2. **[次へ**] を選択し、TXT レコードをドメイン レジストラーに追加して、引き継ぐドメインを所有していることを確認します。

    ウィザードでは、追加する TXT レコードと、レジストラーの Web サイトへのリンク、および詳細な手順へのリンクを提供します。

3. [管理者] ページ **で** 、[ **管理センターに移動**] を選択します。

    管理センターでアカウントを管理するために必要な管理者特権があります。 たとえば、アカウント ユーザーとグループの管理、新しいサブスクリプションの購入、ユーザーの割り当て、アカウント ドメインの管理を行うことができます。

    別のアカウントに追加できるように、このアカウントからドメインを削除する場合は、「別のアカウント [からドメインを削除する](remove-a-domain-from-another-account.md)」を参照してください。
  
## <a name="related-content"></a>関連コンテンツ

YouTube: [Power BI と Microsoft 365 の IT 管理者の引き継ぎを行うための 3 つの手順](https://www.youtube.com/watch?v=xt5EsrQBZZk) (ビデオ)\
[Azure AD での管理者の引き継ぎ](/azure/active-directory/users-groups-roles/domains-admin-takeover) (記事)\
[組織でのセルフサービス サインアップの使用](self-service-sign-up.md) (記事)\
[Power BI サービス管理者ロールについて](/power-bi/service-admin-role) (記事)