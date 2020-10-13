---
title: Microsoft 365 のグローバル管理者アカウントを保護する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: この記事では、グローバル管理者のアクセスを Microsoft 365 サブスクリプションに保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15c497e02b139ea6af4aabba9f3e9ab65a1205be
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445409"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Microsoft 365 のグローバル管理者アカウントを保護する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 サブスクリプションのセキュリティ侵害 (情報の収集、フィッシング攻撃を含む) は、通常、Microsoft 365 のグローバル管理者アカウントの資格情報を侵害することによって行われます。 クラウドのセキュリティは、お互いと Microsoft の間のパートナーシップです。
  
- Microsoft クラウドサービスは、信頼とセキュリティの基礎に基づいて構築されています。 Microsoft は、データとアプリケーションを保護するためのセキュリティ制御と機能を提供しています。
    
- データと id、およびそれらを保護する責任、オンプレミスのリソースのセキュリティ、および管理するクラウドコンポーネントのセキュリティを所有しています。
    
Microsoft は、組織を保護するための機能を提供していますが、使用する場合にのみ有効です。 これらを使用しないと、攻撃にさらされる可能性があります。 全体管理者アカウントを保護するために、Microsoft は次のことを行うための詳細な指示にお役立てください。
  
1. 専用の Microsoft 365 グローバル管理者アカウントを作成し、必要な場合にのみ使用します。
    
2. 専用の Microsoft 365 グローバル管理者アカウントに対して多要素認証を構成し、最強のセカンダリ認証形式を使用します。
    
> [!Note]
> この記事ではグローバル管理者アカウントに重点を置いていますが、電子情報開示管理者やセキュリティまたはコンプライアンス管理者アカウントなど、さまざまな範囲のアクセス許可を持つその他のアカウントを同じ方法で保護する必要があるかどうかを検討する必要があります。 <br > グローバル管理者アカウントは、ライセンスを追加することなく作成できます。
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>手順 1.  専用の Microsoft 365 グローバル管理者アカウントを作成し、必要な場合にのみ使用する

グローバル管理者特権を必要とする、ユーザーアカウントへの役割の割り当てなど、比較的少数の管理タスクがあります。 そのため、グローバル管理者の役割が割り当てられている日常のユーザーアカウントを使用する代わりに、次の手順を実行します。
  
1. グローバル管理者の役割が割り当てられているユーザーアカウントのセットを決定します。 これは、Microsoft 365 管理センターで行うか、次の Azure Active (Azure AD) Directory PowerShell for Graph コマンドを使用して行うことができます。
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. グローバル管理者の役割が割り当てられているユーザーアカウントを使用して、Microsoft 365 サブスクリプションにサインインします。
    
3. 最大4つの専用のグローバル管理者ユーザーアカウントを作成します。 **少なくとも12文字の強力なパスワードを使用してください。** 詳細について [は、「強力なパスワードを作成する](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 」を参照してください。 新しいアカウントのパスワードを安全な場所に格納します。 
    
4. 新しい専用のグローバル管理者ユーザーアカウントに、グローバル管理者の役割を割り当てます。
    
5. Microsoft 365 からサインアウトします。
    
6. 新しい専用のグローバル管理者ユーザーアカウントのいずれかを使用してサインインします。
    
7. 手順1でグローバル管理者の役割が割り当てられている既存のユーザーアカウントごとに、次の操作を行います。
    
  - グローバル管理者ロールを削除します。
    
  - そのユーザーのジョブ機能と責任に応じて、管理者の役割をアカウントに割り当てます。 Microsoft 365 のさまざまな管理者ロールの詳細については、「 [管理者の役割につい](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください。
    
8. Microsoft 365 からサインアウトします。
    
結果は次のようになります。
  
- グローバル管理者ロールを持つ、サブスクリプションのユーザー アカウントのみが、新しい専用のグローバル管理者アカウント セットとなります。 このことを確認するには、次の PowerShell コマンドを使用します。
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- サブスクリプションを管理するその他の通常のユーザー アカウントには、各自の職務に関連する管理ロールが割り当てられています。
    
この時点から、グローバル管理者特権を必要とするタスクに対してのみ、専用のグローバル管理者アカウントを使用してサインインします。 他のすべての Microsoft 365 管理は、他の管理役割をユーザーアカウントに割り当てることによって実行する必要があります。
  
> [!NOTE]
> これには、日常のユーザーアカウントとしてサインアウトし、専用のグローバル管理者アカウントでサインインするための追加の手順が必要になります。 ただし、この操作を実行する必要があるのは、全体管理者の操作の場合だけです。 グローバル管理者アカウント違反がある場合は、さらに多くの手順を実行する必要があるため、Microsoft 365 サブスクリプションを復元することを検討してください。
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>手順 2.  専用の Microsoft 365 グローバル管理者アカウントに対して多要素認証を構成する

多要素認証 (MFA) には、アカウント名とパスワード以外の追加情報が必要です。 Microsoft 365 では、次の追加の検証方法がサポートされています。
  
- Microsoft Authenticator アプリ

- 電話
    
- テキストメッセージを使用して送信された、ランダムに生成された検証コード
    
- スマート カード (仮想または物理)
    
- 生体認証デバイス
    
>[!Note]
>米国標準規格とテクノロジ (NIST) 標準に準拠する必要がある組織では、電話またはテキストメッセージベースの追加の検証方法を使用することは制限されています。 詳細については、 [ここ](https://pages.nist.gov/800-63-FAQ/#q-b01) をクリックしてください。
>

クラウドのみに格納されているユーザーアカウントを使用している小規模な企業 (クラウドのみの id モデル) の場合は、 [mfa を設定](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) して、電話を使用して mfa を構成するか、専用のグローバル管理者アカウントごとにスマートフォンに送信されるテキストメッセージの検証コードを使用します。
    
Microsoft 365 ハイブリッド id モデルを使用している大規模な組織の場合は、さらに多くの検証オプションがあります。 より強力なセカンダリ認証方法に対してセキュリティインフラストラクチャが既に配置されている場合は、 [MFA を設定](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) し、適切な検証方法にそれぞれの専用のグローバル管理者アカウントを構成します。
  
目的の強力な検証方法のセキュリティインフラストラクチャが、Microsoft 365 MFA 用に設置されておらず、機能していない場合は、一時的なセキュリティ対策として、Microsoft Authenticator アプリ、電話、または全体管理者アカウントのスマートフォンに送信されるテキストメッセージ検証コードを使用して、専用のグローバル管理者アカウントを MFA で構成することを MFA で提供される追加の保護を行わずに、専用のグローバル管理者アカウントを残さないようにします。
  
詳細については、「 [Microsoft 365 の MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)」を参照してください。
  
MFA と PowerShell を使用して Microsoft 365 サービスに接続するには、次の記事を参照してください。

- [ユーザーアカウント、グループ、ライセンスのための Microsoft 365 の PowerShell](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>エンタープライズ組織のための追加の保護

これらの追加の方法を使用して、全体管理者アカウントと、それを使用して実行する構成を可能な限り安全なものにすることができます。
  
### <a name="privileged-access-workstation"></a>特権アクセスワークステーション

高い権限を持つタスクの実行が可能な限り安全であることを確認するには、特権アクセスワークステーション (PAW) を使用します。 PAW は、グローバル管理者アカウントを必要とする Microsoft 365 構成などの機密性の高い構成タスクにのみ使用される専用のコンピューターです。 このコンピューターはインターネットブラウジングや電子メールで毎日使用されていないため、インターネット攻撃および脅威から保護するのが適切です。
  
PAW をセットアップする方法については、「」を参照してください [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) 。

Azure AD テナントと管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。

サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」を参照してください。

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

グローバル管理者アカウントにグローバル管理者の役割を永続的に割り当てるのではなく、Azure AD Privileged Identity Management (PIM) を使用して、必要に応じて、グローバル管理者の役割をオンデマンドで一度だけ割り当てられるようにすることができます。
  
グローバル管理者アカウントは、永続的な管理者から適格な管理者に移動します。 グローバル管理者の役割は、ユーザーが必要とするまで非アクティブです。 次に、アクティブ化プロセスを完了して、グローバル管理者の役割を、あらかじめ決められた時間だけグローバル管理者アカウントに追加します。 時間が経過すると、PIM はグローバル管理者アカウントから全体管理者の役割を削除します。
  
PIM を使用すると、このプロセスによって、グローバル管理者アカウントが悪意のあるユーザーの攻撃および使用に対して脆弱になる時間が大幅に短縮されます。

PIM は、Microsoft 365 E5 に含まれている Azure Active Directory Premium P2 で使用できます。 または、管理者アカウントの Azure Active Directory Premium P2 ライセンスを個別に購入できます。
  
詳細については、「 [AZURE AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)」を参照してください。
  

### <a name="privileged-access-management"></a>特権アクセス管理

特権アクセス管理は、テナントでのタスクベースのアクティビティに対して Just-In-Time アクセスを指定するポリシーを構成することで有効になります。これは、機密性の高いデータへの継続的なアクセスや重要な構成設定へのアクセスに、既存の特権管理者アカウントが使用される可能性のある侵害から組織を保護するために役立ちます。たとえば、テナント内の組織のメールボックス設定にアクセスして変更する際には、明示的な承認が必要になる特権アクセス管理ポリシーを構成できます。

この手順では、テナントの特権アクセス管理を有効にして、組織のデータおよび構成設定へのタスクベースのアクセスに対するセキュリティを強化する特権アクセスポリシーを構成します。組織の特権アクセスは、次の 3 つの基本的な手順で開始します。

- 承認者のグループを作成する
- 特権アクセスを有効にする
- 承認ポリシーを作成する

特権アクセス管理を使用すると、組織はゼロに立った特権で運用し、そのような管理アクセスのために発生する脆弱性に対する防御層を提供することができます。 特権アクセスには、関連付けられている承認ポリシーが定義されているタスクを実行するための承認が必要です。 承認ポリシーに含まれるタスクを実行する必要があるユーザーは、要求を行い、アクセス承認を付与する必要があります。

特権アクセス管理を有効にするには、「 [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)」を参照してください。

詳細については、「 [特権アクセス管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)」を参照してください。

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Microsoft 365 ログのセキュリティ情報およびイベント管理 (SIEM) ソフトウェア

サーバー上での SIEM ソフトウェア実行では、アプリケーションとネットワークハードウェアによって作成されたセキュリティ通知とイベントのリアルタイム分析を実行します。 SIEM サーバーに Microsoft 365 のセキュリティの警告とイベントを分析およびレポート機能に含めることができるようにするには、Azure AD をお客様の SEIM に統合します。 「 [Azure ログ統合の概要」を](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview)参照してください。

## <a name="next-step"></a>次のステップ

Microsoft 365 サブスクリプションの id を設定している場合は、次を参照してください。

- クラウドのみの id を使用している場合は、[クラウドのみの id](cloud-only-identities.md)
- ハイブリッド id を使用している場合[にディレクトリ同期を準備](prepare-for-directory-synchronization.md)する

  
## <a name="see-also"></a>関連項目

[Microsoft 365 セキュリティロードマップ](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
