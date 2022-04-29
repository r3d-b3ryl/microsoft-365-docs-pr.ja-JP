---
title: Azure Active Directoryセットアップ ガイド
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
description: Azure Active Directoryのセットアップ ガイドについて説明します。
ms.openlocfilehash: 58f7ed9a20580db742a773cb8a7874137f0cfc4c
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65128414"
---
# <a name="azure-active-directory-setup-guides"></a>Azure Active Directoryセットアップ ガイド

Azure Active Directory (Azure AD) 機能は、組織の管理とセキュリティ保護に役立ちます。 これらのセットアップ ガイドは、これらの機能を簡単な方法で統合するのに役立ちます。 以降のセクションでは、セットアップ ガイドについて簡単に説明し、ガイドへのリンクを共有します。

## <a name="who-are-these-setup-guides-for"></a>これらのセットアップ ガイドはWhoですか?

これらのセットアップ ガイドは、通常、専用の ID チームを持たない小規模から中規模の組織向けに設計されています。 ID エキスパートである必要はありません。

## <a name="what-to-expect-and-what-youll-need"></a>期待する内容と必要なもの

セットアップ ガイドは、Azure ADのコア機能を構成するのに役立ちます。 より高度な構成を設定する必要がある場合は、セットアップ ガイドによって、Azure AD ポータルの適切な場所が示されます。

### <a name="required-permissions"></a>必要なアクセス許可

次の管理ロールのメンバーである必要があります。

- グローバル管理者: セットアップ ガイドの統合ツールを使用して、Microsoft 365組織で変更を行うことができます。

- グローバル リーダー: セットアップ ガイドを表示できますが、テナントで変更を加える必要はありません。

## <a name="identity-security-for-teams"></a>Teamsの ID セキュリティ

Azure Active Directory (Azure AD) は、従業員がアプリやサービスにサインインしてアクセスするのに役立つ、クラウドベースの ID とアクセス管理サービスです。
このカタログには、ユーザーが安全で、Teamsを使用して最も生産性の高い時間を過ごすために使用できる基本的なセキュリティ機能が含まれています。

### <a name="licensing"></a>ライセンス

このカタログのセキュリティ機能を利用するには、Azure Active Directory P2 ライセンスが必要です。

[Teams カタログの ID セキュリティを開く](https://aka.ms/teamsidentity)

## <a name="identity-governance"></a>ID ガバナンス

このウィザード カタログは、Access Reviews (AR)、Privileged Identity Management (PIM)、エンタイトルメント管理 (ELM) など、Azure Active Directory P2 機能を使用するお客様を支援するように設計されています。 PIM とELM では、ドキュメントのキュレーションされた一覧と、管理者がこの機能を構成できるAzure Active Directory管理センターへのポインターを提供しています。 AR の場合、管理者は 2 つのテンプレートから選択できる完全に自動化されたエクスペリエンスを提供します。 これらのテンプレートには、グループ所有者がすべてのMicrosoft 365 グループでゲストの使用を承認できるようにするテンプレートが含まれています。 これは、お客様が現在使用している最も重要なポリシーです。  

次に、テスト テンプレートを提供します。管理者は、選択した特定のグループのゲストの校閲者です。 テナントに、すべてのMicrosoft 365 グループのゲスト ユーザーを対象とするレビューが既にある場合、管理者は既存のレビューを管理するためにAzure Active Directory管理センターを指し示され、自動化されたエクスペリエンスはありません。

[Identity Governance セットアップ ガイドを開く](https://go.microsoft.com/fwlink/p/?linkid=386330)

> [!NOTE]
> このカタログのセキュリティ機能を利用するには、Azure Active Directory P2 ライセンスが必要です。

## <a name="azure-active-directory-deployment"></a>Azure Active Directoryデプロイ  

Azure Active Directoryセットアップ ガイドは、推奨される順序で最も一般的なAzure AD機能を設定するのに役立ちます。 セットアップ ガイドは、 **初期**、 **コア**、 **および詳細設定** の 3 つのセクションに分かれています。 各セクションでは、一連の機能を有効にすることをお勧めします。

セットアップ ガイドには、完了する必要があるタスクのチェックリストが含まれており、ガイドを実行するときに進行状況を追跡できます。 必要に応じて、ガイドは他のセットアップ ガイドにもリンクされます。

[Azure Active Directoryセットアップ ガイドを開きます](https://go.microsoft.com/fwlink/p/?linkid=2183427)。

## <a name="add-or-sync-users-to-your-microsoft-account"></a>Microsoft アカウントにユーザーを追加または同期する  

このガイドは、Azure とMicrosoft 365でユーザー アカウントのセットアップを設定するのに役立ちます。 環境とニーズに基づいて、ユーザーを個別に追加したり、クラウド同期またはAzure AD Connectを使用してオンプレミス ディレクトリAzure AD移行したり、既存の同期の問題のトラブルシューティングを行ったりすることができます。

### <a name="licensing"></a>ライセンス

Azure Active Directory同期ツールの使用は無料で、すべてのMicrosoft 365サブスクリプションに含まれています。

[ユーザーの追加または同期のセットアップ ガイドを開きます](https://go.microsoft.com/fwlink/?linkid=2183349)。

## <a name="secure-your-cloud-apps-with-single-sign-on-sso"></a>シングル サインオン (SSO) を使用してクラウド アプリをセキュリティで保護する

このガイドは、クラウド アプリをMicrosoft 365に追加するのに役立ちます。 このガイドでは、テナントにアプリケーションを追加したり、アプリにユーザーを追加したり、ロールを割り当てたりすることができます。  アプリでシングル Sign-On (SSO) がサポートされている場合は、その構成についても説明します。

### <a name="licensing"></a>ライセンス

Microsoft 365のすべての有料サブスクリプションには、Azure ADへの無料サブスクリプションが付属しています。 Azure ADを使用してアプリを管理し、ユーザー アカウントとグループ アカウントを作成および管理できます。

[セットアップ ガイドにクラウド アプリを追加Microsoft 365開く](https://aka.ms/AzureAppSetup)

## <a name="azure-self-service-password-reset-sspr-guide"></a>Azure Self-Service パスワード リセット (SSPR) ガイド

このセットアップ ガイドは、セルフサービスのパスワード リセットを有効にして構成するのに役立ちます。 セットアップ ガイドでは、パスワードの書き戻しや管理者の通知など、推奨されるオプションについて説明します。

### <a name="licensing"></a>ライセンス

SSPR には、次のいずれかのライセンスが必要です。

- Azure Active Directory P1 または P2

- Microsoft 365 Business Premium

- Microsoft 365 Enterprise E3 または E5  

- Enterprise モビリティとセキュリティ E3 または E5

[セルフサービスのパスワード リセットセットアップ ガイドを開きます](https://go.microsoft.com/fwlink/p/?linkid=2183284)。

## <a name="multi-factor-authentication-mfa"></a>多要素認証 (MFA)

このガイドでは、現在の MFA の状態を示し、IT 管理者が組織の要件を満たす最適な MFA オプションを選択するのに役立ちます。 次に、組織に対して選択した MFA メソッドの構成と適用を支援します。

### <a name="licensing"></a>ライセンス

条件付きアクセスには、Azure Active Directory P1 または P2 ライセンスが必要です。セキュリティの既定値とユーザーごとの MFA は無料で、すべてのMicrosoft 365サブスクリプションに含まれています。

[多要素認証 (MFA) ガイドを開く](https://go.microsoft.com/fwlink/?linkid=2183506)

## <a name="the-passwordless-setup-guide"></a>パスワードレス セットアップ ガイド

パスワードレス セットアップ ガイドは、環境に最適なパスワードレス方法を決定するのに役立ちます。 メソッドには、セキュリティ キー、Windows Hello for Business、Microsoft Authenticator アプリが含まれます。 推奨事項がWindows Hello for Businessされている場合は、さまざまなオプションについて説明するセクションがあります。 このガイドでは、ステップ バイ ステップ プランの作成に役立つ質問が表示されます。

### <a name="licensing"></a>ライセンス

Microsoft 365のすべての有料サブスクリプションには、Azure ADへの無料サブスクリプションが付属しています。 Azure ADを使用してアプリを管理し、ユーザー アカウントとグループ アカウントを作成および管理できます。

[パスワードレス セットアップ ガイドを開きます](https://go.microsoft.com/fwlink/?linkid=2183427)。
