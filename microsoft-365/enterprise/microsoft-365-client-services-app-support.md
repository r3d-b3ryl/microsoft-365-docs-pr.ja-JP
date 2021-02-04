---
title: Microsoft 365 クライアントとサービス アプリのサポート
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: この記事では、Microsoft 365 クライアントとサービス アプリのサポートに関する詳細を確認します。
ms.openlocfilehash: 4e32e39281175ed66970a358ff632c2ddbb3ac1a
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097495"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Microsoft 365 クライアントとサービス アプリのサポート

Microsoft は、お客様のデータを安全に保つさまざまなセキュリティ、認証、コンプライアンス機能をサポートし、IT 管理者がユーザー向け Microsoft 365 管理センター内のポリシーをカスタマイズできます。 次の機能は、Microsoft 365 サブスクリプションに応じて構成できる多くのエンタープライズ機能のサブセットにすすむ機能です。

## <a name="client-and-service-support"></a>クライアントとサービスのサポート

### <a name="continuous-access-evaluation-preview"></a>継続的なアクセスの評価 (プレビュー)

継続的なアクセス評価は、Exchange Online、SharePoint Online、Teams などのサービスが Azure Active Directory の重要なイベントをサブスクライブして、それらのイベントをほぼリアルタイムで評価および適用できるようすることで実装されます。 重要なイベントの評価は条件付きアクセス ポリシーに依存しないので、どのテナントでも利用できます。

現在、次のイベントが評価されています。

- ユーザー アカウントが削除または無効化されている
- ユーザーのパスワードが変更またはリセットされる
- ユーザーに対して多要素認証が有効になっている
- 管理者がユーザーのすべての更新トークンを明示的に取り消す
- Azure AD Identity Protection によって検出されたユーザー リスクの引き上

クライアントおよびサービス アプリサポートの継続的なアクセス評価の詳細については、「継続的なアクセスの評価 (プレビュー)」を [参照してください](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)。

## <a name="client-support"></a>クライアント サポート

### <a name="certificate-based-authentication"></a>証明書ベースの認証

証明書ベース認証 (CBA) は、リソース、ネットワーク、アプリケーション、またはサービスへのアクセスを許可する前に、デジタル証明書を使用してユーザー、コンピューター、またはデバイスを識別します。 ユーザー認証では、多くの場合、ユーザー名やパスワードなどの従来の方法と連携して展開されます。

一部の従来のソリューションは、生体認証やワンタイム パスワード (OTP) など、ユーザーにのみ機能します。 証明書ベースの認証では、すべてのエンドポイントで同じソリューションを使用できます。ユーザー、デバイス、および増大するモノのインターネット (IoT)

クライアントおよびサービス アプリのサポートに対する証明書ベースの認証の詳細については [、「Microsoft 365 Client App Support: Certificate-based Authentication 」を参照してください](microsoft-365-client-support-certificate-based-authentication.md)。

### <a name="conditional-access"></a>条件付きアクセス

条件付きアクセスは、シグナルをまとめ、決定を下し、組織のアクセス ポリシーを適用するために Azure Active Directory で使用されるツールです。 条件付きアクセスは、新しい ID 駆動型コントロール モデルの中心です。

条件付きアクセス ポリシーは、リソースへのアクセスを許可する if-then ステートメントです。 ユーザーがリソースにアクセスする場合、ユーザーはアクションを完了する必要があります。 ポリシー アクセスの決定時に条件付きアクセスで使用できる一般的なシグナルは次のとおりです。

- ユーザーまたはグループメンバーシップ
- IP の場所情報
- デバイス情報
- アプリケーション情報
- リアルタイムおよび計算されたリスク検出
- Microsoft Cloud App Security (MCAS)

これらのアクセス決定を行う場合、ポリシーは異なるアクションを実行できます。

- ポリシーはアクセスをブロックできます。この構成は、最も制限の厳しいアクションであり、ユーザーがリソースにアクセスしなくはありません。
- ポリシーはアクセスを許可できます。この構成は制限の少ない決定であり、次のオプションの 1 つ以上が引き続き必要な場合があります。

    - 多要素認証
    - 準拠としてマークするデバイス
    - デバイスがハイブリッド Azure ADされている
    - 承認されたクライアント アプリ
    - アプリ保護ポリシーの構成 (プレビュー)

クライアントおよびサービス アプリサポートの条件付きアクセスの詳細については、以下を参照してください。

- [Microsoft 365 クライアント アプリのサポート: デバイス ベースの条件付きアクセス](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>モバイル アプリケーション管理

多くの場合、ユーザーは同じモバイル デバイスから組織と個人のドキュメント、電子メール、データの両方にアクセスします。 多くの場合、これらのデバイスは個人所有であり、組織データとユーザーの個人プライバシーの両方を保護するように構成する必要があります。

ユーザーが組織データにアクセスする場合、組織は、デバイス上の組織データを保護するために、構成ポリシーや保護ポリシーなどの組織ポリシーが適用されるという確信を持つ必要があります。 さらに、デバイス上のユーザーの個人コンテンツは、組織の制御の外部に残る必要があります。

組織で管理されるコンテンツの場合は、アプリケーション管理ポリシーを適用して、Microsoft Intune を使用してデータへのアクセス、共有、および使用方法を制御できます。 たとえば、次のアクションがサポートされています。

- 管理された組織のコンテンツ (組織データとも呼ばれます) をリモート ワイプする
- 組織のコンテンツを組織以外の場所に貼り付け防止する
- 組織のコンテンツにアクセスするために PIN を要求する
- 管理対象アプリが脱獄またはルートデバイスで実行されるのを防ぐ
- 未承認のクラウド ストレージ プロバイダーに組織のコンテンツが保存されるのを防ぐ
- 承認されていないコンテンツが管理対象アプリケーションに転送されるのを防ぐ
- ポリシーが適用された後にのみ組織のコンテンツへのアクセスを許可する
- アプリケーションの動作と設定を管理するアプリケーション構成を提供する
- 複数 ID 機能または個人使用を無効にして、管理アプリケーションを定義済みの ID に制限する

Microsoft Intune を使用したモバイル アプリケーション管理の詳細については、「Microsoft Intune アプリ管理 [とは」を参照してください。](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>多要素認証

[多要素認証 (MFA) は、複数の独立した証拠を認証メカニズムに正常に提示した後にのみユーザーにアクセスを許可するコンピューター アクセス制御の方法です。 このメソッドは、通常、次のカテゴリのうち少なくとも 2 つを使用します。

- 知識 (知っているもの)
- 所有 (持っているもの)
- 一貫性 (何か)

クライアントおよびサービス アプリサポートの多要素認証の詳細については [、「Microsoft 365 Client App Support: Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md)」を参照してください。

### <a name="single-sign-on"></a>シングル サインオン

シングル サインオン (SSO) を使用すると、ユーザーが Azure Active Directory のアプリケーションにサインオンするときにセキュリティと利便性が向上します。 シングル サインオンでは、ユーザーは 1 つのアカウントで 1 回サインインして、オンプレミスの Active Directory ドメイン サービス (AD DS) ドメインに参加しているデバイス、サービスとしてのソフトウェア (SaaS) アプリケーション、および組織内の Web アプリケーションにアクセスします。

クライアントおよびサービス アプリサポートのシングル サインオンの詳細については [、「Microsoft 365 Client App Support: Single sign-on](microsoft-365-client-support-single-sign-on.md)」を参照してください。

## <a name="services-support"></a>サービス のサポート

### <a name="modern-authentication"></a>先進認証

モダン認証を使用すると、お客様が Office 365 に対して認証を行い、テナント管理者が Office 365 テナンシー全体で次のような特定の認証要件を適用するための新しいシナリオが可能になります。

- テナンシーとサービスとの管理操作、およびアプリケーションとそのデータに対するエンド ユーザーの操作に対する多要素認証のサポート
- 条件付きアクセス
- SAML ベースのサードパーティ ID プロバイダーのサインイン
- パーソナル コンピューター上のスマートカード ログ
- モバイル デバイスでの証明書ベースの認証
- 基本認証を使用して資格情報を送信する必要がなくなりました。

最新の認証サービスのサポートの詳細については、「認証と承認」を [参照してください](/azure/active-directory/develop/authentication-vs-authorization)。

### <a name="azure-active-directory-conditional-access"></a>Azure Active Directory 条件付きアクセス

Azure Active Directory (Azure AD) の条件付きアクセス ルールにより、お客様はデバイスのコンプライアンスやネットワークの場所などの属性に基づいて、オンライン サービスへのアクセスを制御できます。 次のソリューションを使用できます。

- Azure AD多要素認証ベースの条件付きアクセス
- Azure ADベースの条件付きアクセス
- Azure ADデバイス ベースの条件付きアクセス

Azure AD条件付きアクセス ルールはアプリケーションごとに適用され、ユーザーはさまざまな条件に基づいてアクセスを制御できます。 モバイル デバイス管理 [(MDM)](/mem/intune/fundamentals/what-is-device-management)または Intune を使用すると、組織のデバイスを使用しているユーザー、または管理のために個人用デバイスを登録したユーザーにのみ、Microsoft 365 へのアクセスを制限できる必要があります。 たとえば、お客様は次のようなコントロールを適用するために条件付きアクセス ルールを構成できます。

- ドメインに参加しているデバイスまたはドメインに準拠しているデバイスからのアクセスのみを許可する
- Exchange Online サービスへのすべてのアクセスに対して多要素認証を適用する

Azure Active Directory 条件付きアクセスの詳細については、「条件付きアクセス [とは」を参照してください。](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>TLS 1.2 のサポート

お客様にクラス最高の暗号化を提供するために、Microsoft は Office 365 および Office 365 GCC のトランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 のサポートを中止する予定です。

お客様のデータに対するセキュリティの重要性を理解すると共に、お客様が利用しているサービスに影響を及ぼす可能性のある変更については、その情報を公開することをお約束いたします。 すべてのクライアント サーバーとブラウザー サーバーの組み合わせで TLS 1.2 (以降のバージョン) を使用して、Office 365 サービスへの接続を維持することをお勧めします。 クライアントとサーバー間、ブラウザーとサーバー間の特定の組み合わせについては、更新が必要になる場合があります。

TLS 1.2 のサポートとサービスのサポートの詳細については [、「Office 365 および Office 365 GCC での TLS 1.2](/microsoft-365/compliance/prepare-tls-1.2-in-office-365)の準備」を参照してください。
