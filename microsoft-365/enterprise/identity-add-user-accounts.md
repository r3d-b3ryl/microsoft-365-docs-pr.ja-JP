---
title: '手順 4: ユーザ アカウントを追加する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: ユーザー アカウントとグループを、クラウドに直接追加するか、オンプレミス ディレクトリと同期することにより追加します。
ms.openlocfilehash: 2a54044737f5b924bd619d5a6c7c72091dc7a0d1
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005836"
---
# <a name="step-4-add-your-user-accounts"></a>手順 4: ユーザ アカウントを追加する

![フェーズ 2 - ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a>クラウド専用 ID のユーザー アカウントを作成する

クラウド専用 ID の場合、Azure Active Directory (Azure AD) にユーザーとグループを作成します。 使用できるもの:

- Microsoft 365 管理センター
- Azure portal
- Azure PowerShell

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a>ハイブリッド ID の ID を同期する

*これはハイブリッド環境で必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

このセクションでは、オンプレミス Active Directory Domain Services (AD DS) を、Office 365、Microsoft Intune、Microsoft 365 Enterprise に含まれるその他のクラウドベースのサービスで使用される Azure AD テナントに同期させます。

Azure AD Connect は、シングル フォレストまたはマルチフォレスト AD DS 環境の実際に必要な ID のみを、Azure AD テナントと同期できるようにする、サポートされている Microsoft ツールです。 次の図は、Azure AD Connect 同期に関する基本的なプロセスを示します。

![Azure AD Connect によるオンプレミス ディレクトリと Azure AD の同期方法](../media/identity-add-user-accounts/azure-ad-connect.png)

1. サーバーで実行している Azure AD Connect は、アカウント、グループ、および連絡先の変更に関して AD DS にポーリングします。
2. Azure AD Connect はそれらの変更を Microsoft 365 サブスクリプションの Azure AD テナントに送信します。

The first decision in your hybrid identity solution is your authentication requirement. The following options are options:

- With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication: 
    - **パスワード ハッシュ同期 (PHS)**: (一部のプレミアム機能で推奨または必須) Azure AD でオンプレミス ディレクトリ オブジェクトの認証を有効にする最も簡単な方法です。 Azure AD Connect は AD DS からハッシュ化されたパスワードを抽出し、パスワード ハッシュに対し追加のセキュリティ処理を実行し、パスワードを Azure AD に同期します。 詳細については、「[Azure AD Connect 同期を使用したパスワード ハッシュ同期の実装](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)」を参照してください。
    - **パススルー認証 (PTA)**: Azure AD ベース サービスのためのシンプルなパスワード検証ソリューションです。 PTA は 1 つ以上のオンプレミス サーバーで実行されているエージェントを使用して、オンプレミス AD DS に対し直接ユーザー認証を検証します。 詳細については、「[Azure Active Directory パススルー認証によるユーザー サインイン](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)」を参照してください。
- With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn).

Microsoft 365 Enterprise の ID モデルと認証の概要については、このビデオをご覧ください。

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

ハイブリッド ID ソリューションが決定したら、[IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) をダウンロードして実行し、AD DS を分析して問題がないかどうかを確認します。

IdFix ツールで検出されたすべての問題を解決したら、Azure AD Connect ツールのインストール、および Microsoft 365 サブスクリプションのオンプレミス AD DS と Azure AD テナント間のディレクトリ同期の構成に関するガイダンスとして「[パスワード ハッシュ同期の実装](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)」を参照してください。 同期開始後は、オンプレミス ID プロバイダー (AD DS など) でユーザー アカウントとグループを維持できます。

Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。 

- ハイブリッド環境で推奨されている要件については、[前提条件](identity-access-prerequisites.md#prerequisites)の**パスワード ハッシュ同期を使用した Active Directory** をご覧ください。 

- クラウド専用環境で推奨されている要件については、[前提条件](identity-access-prerequisites.md#prerequisites)の**クラウドのみ**列をご覧ください。

Azure AD にオンプレミスのユーザーとグループが作成されると、 OneDrive for Business や Exchange Online などのライセンスの割り当てと、生産性ワークロードの使用を開始できます。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: パスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)<br> [テスト ラボ ガイド: パススルー認証](pass-through-auth-m365-ent-test-environment.md) |
|||

中間チェックポイントとして、このセクションに対応する[終了条件](identity-exit-criteria.md#crit-identity-sync)を確認できます。

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>同期の状態を監視する

*この手順はオプションであり、Microsoft 365 のバージョン E3 および E5 の両方に適用されます。*

このセクションでは、Azure AD Connect Health エージェントを各オンプレミス AD DS ドメイン コントローラーにインストールして、Azure AD Connect によって提供されている ID インフラストラクチャと 同期サービスを監視します。 監視情報は Azure AD Connect Health ポータルで使用可能になります。このポータルでは、アラート、パフォーマンス監視、使用状況分析などの情報を確認できます。

![Azure AD Connect Health のコンポーネント](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

Azure AD Connect Health の使用法に関する重要な設計上の決定は、Azure AD Connect をどのように使用しているかに応じて異なります。

- **管理認証**オプションを使用している場合は、最初に「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」を参照し、Azure AD Connect Health について理解し、構成します。
- Active Directory フェデレーション サービス (AD FS) で**フェデレーション認証**を使用してアカウントとグループの名前だけを同期している場合は、最初に「[Azure AD Connect Health を使用した AD FS の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」を参照し Azure AD Connect Health について理解し、構成します。

このセクションの完了後の成果物は次のとおりです。

- Azure AD Connect Health エージェントがオンプレミス ID プロバイダー サーバーにインストールされている。
- Azure AD Connect Health ポータルでは、Microsoft 365 サブスクリプションの Azure AD テナントでオンプレミス インフラストラクチャの現在の状態と同期アクティビティを表示しています。

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-sync-health)を確認できます。



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>パスワードの更新を簡素化する

*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*

このセクションでは、ユーザーに Azure Active directory (Azure AD) を通じてパスワードを再設定することを許可します。この再設定はローカル Active Directory Domain Services (AD DS) に複製されます。 このプロセスは、パスワードの書き戻しと呼びます。 ユーザーはパスワードの書き戻しを使用すれば、ユーザー アカウントとその属性が保存されているオンプレミス AD DS を通じてパスワードの更新を行う必要がありません。 これは、オンプレミスのネットワークへのリモート アクセス接続を持たないローミング ユーザーやリモート ユーザーにとって役立ちます。

パスワードの書き戻しは、Azure AD Identity Protection 機能 (アカウント侵害が発生する可能性が高い危険が検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。

その他の情報と構成手順については、「[Azure AD SSPR とパスワード書き戻し](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)」を参照してください。

>[!Note]
>Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: パスワードの書き戻し](password-writeback-m365-ent-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pw-writeback)を確認できます。

|||
|:-------|:-----|
|![手順 5](../media/stepnumbers/Step5.png)| [管理にグループを使用する](identity-use-group-management.md) |
