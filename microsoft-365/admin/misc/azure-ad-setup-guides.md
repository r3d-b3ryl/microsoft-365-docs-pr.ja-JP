---
title: Azure Active Directoryセットアップ ガイド
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
description: 詳細については、このページのセットアップ ガイドAzure Active Directory。
ms.openlocfilehash: 059890bd6a79ced1f7121e973b070790dffd8db9
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403613"
---
# <a name="azure-active-directory-setup-guides"></a>Azure Active Directoryセットアップ ガイド

Azure Active Directory (Azure AD) 機能は、組織の管理とセキュリティ保護に役立ちます。 これらのセットアップ ガイドは、これらの機能を簡単な方法で統合するのに役立ちます。 次のセクションでは、セットアップ ガイドについて簡単に説明し、ガイドへのリンクを共有します。

## <a name="who-are-these-setup-guides-for"></a>Whoセットアップ ガイドは何ですか?

これらのセットアップ ガイドは、一般に専用の ID チームを持たない可能性がある小規模から中規模の組織向けです。 ID エキスパートである必要はありません。

## <a name="what-to-expect-and-what-youll-need"></a>何を期待し、何が必要か

セットアップ ガイドは、ユーザーのコア機能を構成するのに役立Azure AD。 より高度な構成を設定する必要がある場合は、セットアップ ガイドによって、ポータル内の適切な場所Azure ADされます。

### <a name="required-permissions"></a>必要なアクセス許可

次の管理役割のメンバーである必要があります。

- グローバル管理者: セットアップ ガイドの統合ツールを使用して、組織で変更Microsoft 365できます。

- グローバル リーダー: セットアップ ガイドを表示できますが、テナントでは変更を加えできません。

## <a name="identity-security-for-teams"></a>ユーザーの ID セキュリティTeams

Azure Active Directory (Azure AD) はクラウドベースの ID およびアクセス管理サービスで、従業員がサインインしてアプリやサービスにアクセスするのに役立ちます。
このカタログには、ユーザーが安全で、ユーザーの安全を確保し、ユーザーの作業時間を最も高くするために使用できる基本的なセキュリティ機能がTeams。

### <a name="licensing"></a>ライセンス

このAzure Active Directoryのセキュリティ機能を利用するには、P2 ライセンスが必要です。

[Id のセキュリティを開くカタログTeamsします。](https://aka.ms/teamsidentity)

## <a name="azure-active-directory-deployment"></a>Azure Active Directory展開  

このAzure Active Directoryガイドは、推奨される順序で最も一般的Azure AD機能をセットアップするのに役立ちます。 セットアップ ガイドは、Initial、 **Core**、 **Advanced の 3 つのセクション** に分 **かっています**。 各セクションでは、有効にする必要がある一連の機能をお勧めします。

セットアップ ガイドには、完了する必要があるタスクのチェックリストが含まれています。ガイドを進むにつれて進捗状況を追跡できます。 ガイドは、必要に応じて他のセットアップ ガイドにもリンクします。

[セットアップ ガイドAzure Active Directory開きます](https://go.microsoft.com/fwlink/p/?linkid=2183427)。

## <a name="add-or-sync-users-to-your-microsoft-account"></a>Microsoft アカウントにユーザーを追加または同期する  

このガイドは、Azure とユーザー アカウントのセットアップをセットアップMicrosoft 365。 環境とニーズに基づいて、ユーザーを個別に追加するか、Azure AD クラウド同期または Azure AD Connect を使用してオンプレミス ディレクトリを移行するか、既存の同期の問題のトラブルシューティングを行います。

### <a name="licensing"></a>ライセンス

同期Azure Active Directoryを使用すると無料で、すべてのサブスクリプションにMicrosoft 365されます。

[[ユーザーの追加と同期] セットアップ ガイドを開きます](https://go.microsoft.com/fwlink/?linkid=2183349)。

## <a name="add-a-cloud-app-to-microsoft-365"></a>クラウド アプリをアプリに追加Microsoft 365 

このガイドは、クラウド アプリをアプリに追加するのに役立Microsoft 365。 このガイドでは、テナントにアプリケーションを追加し、ユーザーをアプリに追加し、役割を割り当てることができます。  アプリがシングル Sign-On (SSO) をサポートしている場合は、その構成について説明します。

### <a name="licensing"></a>ライセンス

すべての有料サブスクリプションには、Microsoft 365無料のサブスクリプションが付属Azure AD。 アプリを管理しAzure ADユーザー アカウントとグループ アカウントを作成および管理する場合に使用できます。

[[クラウド アプリの追加] セットアップ ガイドMicrosoft 365開きます。](https://aka.ms/AzureAppSetup)

## <a name="azure-self-service-password-reset-sspr-guide"></a>Azure Self-Service パスワードリセット (SSPR) ガイド

このセットアップ ガイドは、セルフサービス パスワードのリセットを有効にして構成するのに役立ちます。 セットアップ ガイドでは、パスワードの書き戻しや管理者の通知など、推奨されるオプションについて説明します。

### <a name="licensing"></a>ライセンス

SSPR には、次のいずれかのライセンスが必要です。

- Azure Active Directory P1 または P2

- Microsoft 365 Business Premium

- Microsoft 365 Enterprise E3 または E5  

- Enterpriseモビリティとセキュリティ E3 または E5

[セルフサービス のパスワード リセットセットアップ ガイドを開きます](https://go.microsoft.com/fwlink/p/?linkid=2183284)。

## <a name="multi-factor-authentication-mfa"></a>多要素認証 (MFA)

このガイドでは、現在の MFA 状態を提供し、IT 管理者が組織の要件を満たす最適な MFA オプションを選択するのに役立ちます。 次に、組織の選択した MFA メソッドの構成とエンフォースを支援します。

### <a name="licensing"></a>ライセンス

条件付きアクセスには、Azure Active Directory P1 または P2 ライセンスが必要です。セキュリティの既定値とユーザーごとの MFA は無料で、すべてのサブスクリプションMicrosoft 365されます。

[多要素認証 (MFA) ガイドを開く](https://go.microsoft.com/fwlink/?linkid=2183506)

## <a name="the-passwordless-setup-guide"></a>パスワードレスセットアップ ガイド

パスワードレスセットアップ ガイドは、環境に最適なパスワードレス方法を決定するのに役立ちます。 このメソッドには、セキュリティ キー、Windows Hello、およびアプリMicrosoft Authenticatorがあります。 おすすめがビジネス向Windows Hello場合は、さまざまなオプションについて説明するセクションがあります。 ガイドでは、ステップ バイ ステッププランの作成に役立つ質問が表示されます。

### <a name="licensing"></a>ライセンス

すべての有料サブスクリプションには、Microsoft 365無料のサブスクリプションが付属Azure AD。 アプリを管理しAzure ADユーザー アカウントとグループ アカウントを作成および管理する場合に使用できます。

[パスワードレスセットアップ ガイドを開きます](https://go.microsoft.com/fwlink/?linkid=2183427)。
