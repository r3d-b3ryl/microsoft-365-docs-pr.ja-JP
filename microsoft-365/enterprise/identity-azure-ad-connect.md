---
title: '手順 7: ID を同期する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ID オプションを理解し、オンプレミス Windows Server AD を Azure AD と同期するように Azure AD Connect を構成します。
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869073"
---
# <a name="step-7-synchronize-identities"></a>手順 7: ID を同期する

*この手順はハイブリッド環境で必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、オンプレミス Windows Server Active Directory (AD) と、Office 365 および Enterprise Mobility + Security (EMS) のサブスクリプションで使用される Azure Active Directory (AD) テナントを同期します。

Azure AD Connect は、シングル フォレストまたはマルチフォレスト Windows Server AD 環境の実際に必要な ID のみを、Azure AD テナントと同期できるようにする、サポートされている Microsoft ツールです。

![Azure AD Connect によるオンプレミス ディレクトリと Azure AD の同期方法](./media/identity-azure-ad-connect/azure-ad-connect.png)

*Azure AD Connect によるオンプレミス ディレクトリと Azure AD の同期方法*

ハイブリッド ID ソリューションでは、最初に認証の要件を決定します。次にオプションを示します。

- **管理認証**では、Azure AD はユーザー サインインの認証プロセスを処理します。管理認証方式は 2 種類あります。 
    - **パスワード ハッシュ同期 (PHS)**: (一部のプレミアム機能で推奨または必須) Azure AD でオンプレミス ディレクトリ オブジェクトの認証を有効にする最も簡単な方法です。Azure AD Connect は Windows Server AD からハッシュ化されたパスワードを抽出し、パスワードに対し追加のセキュリティ処理を実行し、パスワードを Azure AD に保存します。詳細については、「[Azure AD Connect 同期を使用したパスワード ハッシュ同期の実装](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)」を参照してください。
    - **パススルー認証 (PTA)**: Azure AD ベース サービスのためのシンプルなパスワード検証ソリューションです。PTA は 1 つ以上のオンプレミス サーバーで実行されているエージェントを使用して、オンプレミス Windows Server AD に対し直接ユーザー認証を検証します。詳細については、「[Azure Active Directory パススルー認証によるユーザー サインイン](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)」を参照してください。
- **フェデレーション認証**では、ユーザーのサインインで、認証プロセスが ID フェデレーション サーバー (Active Directory フェデレーション サービス (AD FS) など) を介して別の ID プロバイダーにリダイレクトされます。ID プロバイダーは、その他の認証方式 (スマートカード ベースの認証など) を提供できます。詳細については、「[Azure Active Directory ハイブリッド ID ソリューションの適切な認証方法を選択する](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)」を参照してください。

ハイブリッド ID ソリューションが決定したら、[IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) をダウンロードして実行し、Windows Server AD を分析して問題がないかどうかを確認します。

IdFix ツールで検出されたすべての問題を解決したら、「[パスワード ハッシュ同期を実装する](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)」を参照し、Azure AD Connect ツールのインストールと、Office 365 および EMS サブスクリプションのオンプレミス Windows Server AD と Azure AD テナント間のディレクトリ同期の構成について確認してください。同期開始後は、オンプレミス ID プロバイダー (Windows Server AD など) でユーザー アカウントとグループを維持できます。

Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。 
- ハイブリッド環境で推奨されている要件については、[前提条件](identity-access-prerequisites.md#prerequisites)の**パスワード ハッシュ同期を使用した Active Directory** をご覧ください。 

- クラウド専用環境で推奨されている要件については、[前提条件](identity-access-prerequisites.md#prerequisites)の**クラウドのみ**列をご覧ください。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: パスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)<br> [テスト ラボ ガイド: パススルー認証](pass-through-auth-m365-ent-test-environment.md) |
|||

中間チェックポイントとして、この手順に対応する[終了条件](identity-exit-criteria.md#crit-identity-sync)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [同期の状態を監視する](identity-azure-ad-connect-health.md) |

