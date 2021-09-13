---
title: グローバル管理者Microsoft 365アカウントを保護する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
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
description: この記事では、サブスクリプションへのグローバル管理者アクセスの保護に関Microsoft 365します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3a43c8b6ac5389be99581302c249e431853ba99b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215783"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>グローバル管理者Microsoft 365アカウントを保護する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 サブスクリプションのセキュリティ侵害 (情報の収集やフィッシング攻撃など) は、通常、Microsoft 365 グローバル管理者アカウントの資格情報を侵害することで行われます。 クラウドのセキュリティは、お客様と Microsoft のパートナーシップです。
  
- Microsoft クラウド サービスは、信頼とセキュリティの基盤の上に構築されています。 Microsoft は、データとアプリケーションの保護に役立つセキュリティ制御と機能を提供します。
    
- ユーザーは、データと ID、およびデータを保護する責任、オンプレミス リソースのセキュリティ、および制御するクラウド コンポーネントのセキュリティを所有します。
    
Microsoft では、組織の保護に役立つ機能を提供していますが、組織を使用する場合にのみ有効です。 それらを使用しない場合は、攻撃に対して脆弱になる可能性があります。 グローバル管理者アカウントを保護するために、Microsoft は以下の詳細な手順を支援します。
  
1. グローバル管理者アカウントMicrosoft 365作成し、必要な場合にのみ使用します。
    
2. グローバル管理者アカウントに対して専用のMicrosoft 365を構成し、最も強力な形式のセカンダリ認証を使用します。
    
> [!Note]
> この記事ではグローバル管理者アカウントを中心に説明しますが、電子情報開示管理者やセキュリティ管理者アカウント、コンプライアンス管理者アカウントなど、サブスクリプション内のデータにアクセスするための広範なアクセス許可を持つ追加のアカウントを同じ方法で保護するかどうかを検討する必要があります。 <br > グローバル管理者アカウントは、ライセンスを追加せずに作成できます。
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>手順 1. グローバル管理者アカウントMicrosoft 365専用のアカウントを作成し、必要な場合にのみ使用する

役割をユーザー アカウントに割り当てるなど、グローバル管理者特権を必要とする管理タスクは比較的少ない。 したがって、グローバル管理者の役割が割り当てられている日常のユーザー アカウントを使用する代わりに、次の手順を実行します。
  
1. グローバル管理者の役割が割り当てられているユーザー アカウントのセットを決定します。 この操作は、Microsoft 365 管理センターまたは次の Azure Active (Azure AD) ディレクトリ PowerShell Graphします。
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. グローバル管理者ロールMicrosoft 365されているユーザー アカウントを使用して、サブスクリプションにサインインします。
    
3. 最大 4 つの専用グローバル管理者ユーザー アカウントを作成します。 **12 文字以上の強力なパスワードを使用します。** 詳細については [、「強力なパスワードを作成する](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 」を参照してください。 新しいアカウントのパスワードを安全な場所に保存します。 
    
4. 新しい専用のグローバル管理者ユーザー アカウントのそれぞれにグローバル管理者役割を割り当てる。
    
5. アカウントからサインアウトMicrosoft 365。
    
6. 新しい専用のグローバル管理者ユーザー アカウントのいずれかを使用してサインインします。
    
7. 手順 1 からグローバル管理者ロールが割り当てられた既存のユーザー アカウントごとに、次の手順を実行します。
    
  - グローバル管理者の役割を削除します。
    
  - そのユーザーのジョブ機能と責任に適したアカウントに管理者の役割を割り当てます。 管理者ロールの詳細については、「管理役割[Microsoft 365」を参照してください](/office365/admin/add-users/about-admin-roles)。
    
8. アカウントからサインアウトMicrosoft 365。
    
結果は次の値になります。
  
- グローバル管理者ロールを持つ、サブスクリプションのユーザー アカウントのみが、新しい専用のグローバル管理者アカウント セットとなります。 これを確認するには、次の PowerShell コマンドを使用します。
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- サブスクリプションを管理するその他の通常のユーザー アカウントには、各自の職務に関連する管理ロールが割り当てられています。
    
この瞬間以降は、グローバル管理者特権を必要とするタスクに対してのみ、専用のグローバル管理者アカウントでサインインします。 他のすべての管理Microsoft 365、他の管理役割をユーザー アカウントに割り当てる必要があります。
  
> [!NOTE]
> これには、日常のユーザー アカウントとしてサインアウトし、専用のグローバル管理者アカウントでサインインするための追加の手順が必要です。 ただし、これはグローバル管理者の操作に対して時折行う必要があります。 グローバル管理者アカウント侵害後にMicrosoft 365サブスクリプションを回復するには、さらに多くの手順が必要です。
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>手順 2。 グローバル管理者アカウント専用の複数要素認証Microsoft 365構成する

多要素認証 (MFA) には、アカウント名とパスワード以外の追加情報が必要です。 Microsoft 365は、次の追加の検証方法をサポートしています。
  
- Microsoft Authenticator アプリ

- 電話
    
- テキスト メッセージを介して送信されるランダムに生成された検証コード
    
- スマート カード (仮想または物理)
    
- 生体認証デバイス
    
>[!Note]
>国立標準技術研究所 (NIST) の標準に準拠する必要がある組織では、電話またはテキスト メッセージベースの追加検証方法の使用が制限されます。 詳細 [については、](https://pages.nist.gov/800-63-FAQ/#q-b01) ここをクリックしてください。
>

クラウドにのみ保存されているユーザー アカウント (クラウド専用 ID モデル) を使用している小規模企業の場合は、MFA を設定して、電話または専用のグローバル管理者アカウントごとにスマートフォンに送信されるテキスト メッセージ検証コードを使用して [MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) を構成します。
    
ハイブリッド ID モデルを使用している大規模な組織Microsoft 365、より多くの検証オプションがあります。 より強力なセカンダリ認証方法のセキュリティ インフラストラクチャが既に用意されている場合は [、MFA](../admin/security-and-compliance/set-up-multi-factor-authentication.md) をセットアップし、各専用のグローバル管理者アカウントを適切な検証方法用に構成します。
  
必要な強力な検証方法のセキュリティ インフラストラクチャが Microsoft 365 MFA に対して機能していない場合は、Microsoft Authenticator アプリ、電話、または暫定的なセキュリティ対策として、グローバル管理者アカウント用にスマートフォンに送信されるテキスト メッセージ検証コードを使用して、MFA を使用して専用のグローバル管理者アカウントを構成することを強く推奨します。 MFA によって提供される追加の保護がない場合は、専用のグローバル管理者アカウントを残しません。
  
詳細については[、「MFA for Microsoft 365」 を参照してください](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)。
  
MFA と PowerShell Microsoft 365サービスに接続するには、次の記事を参照してください。

- [ユーザー アカウントMicrosoft 365ライセンスの PowerShell](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](/microsoftteams/teams-powershell-install)
- [Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>エンタープライズ組織の追加の保護

これらの追加の方法を使用して、グローバル管理者アカウントと、それを使用して実行する構成が可能な限り安全に保護されます。
  
### <a name="privileged-access-workstation"></a>特権アクセス ワークステーション

高い特権を持つタスクの実行を可能な限り安全に実行するには、特権アクセス ワークステーション (PAW) を使用します。 PAW は、グローバル管理者アカウントを必要とする構成などの機密性の高い構成タスクMicrosoft 365専用のコンピューターです。 このコンピューターはインターネットの閲覧や電子メールには毎日使用されないので、インターネット攻撃や脅威から保護されます。
  
PAW を設定する方法の手順については、「. [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices)

Azure AD テナントと管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。

サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](/azure/active-directory/admin-roles-best-practices)」を参照してください。

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

グローバル管理者アカウントにグローバル管理者ロールを完全に割り当てるのではなく、Azure AD Privileged Identity Management (PIM) を使用して、必要に応じてグローバル管理者ロールのオンデマンドの Just-in-time 割り当てを有効にできます。
  
グローバル管理者アカウントは、永続的な管理者から対象となる管理者に移動します。 グローバル管理者の役割は、誰かが必要とするまで非アクティブです。 その後、アクティブ化プロセスを完了して、グローバル管理者の役割を所定の時間グローバル管理者アカウントに追加します。 時間が経過すると、PIM はグローバル管理者アカウントからグローバル管理者の役割を削除します。
  
PIM とこのプロセスを使用すると、グローバル管理者アカウントが悪意のあるユーザーによる攻撃や使用に対して脆弱になる時間が大幅に短縮されます。

PIM は、Microsoft 365 E5 に含まれている Azure Active Directory Premium P2 で使用できます。 または、管理者アカウントの Azure Active Directory Premium P2 ライセンスを個別に購入できます。
  
詳細については、「Azure AD Privileged Identity Management」[を参照してください](/azure/active-directory/active-directory-privileged-identity-management-configure)。
  

### <a name="privileged-access-management"></a>特権アクセス管理

特権アクセス管理は、テナントでのタスクベースのアクティビティに対して Just-In-Time アクセスを指定するポリシーを構成することで有効になります。これは、機密性の高いデータへの継続的なアクセスや重要な構成設定へのアクセスに、既存の特権管理者アカウントが使用される可能性のある侵害から組織を保護するために役立ちます。たとえば、テナント内の組織のメールボックス設定にアクセスして変更する際には、明示的な承認が必要になる特権アクセス管理ポリシーを構成できます。

この手順では、テナントの特権アクセス管理を有効にして、組織のデータおよび構成設定へのタスクベースのアクセスに対するセキュリティを強化する特権アクセスポリシーを構成します。組織の特権アクセスは、次の 3 つの基本的な手順で開始します。

- 承認者のグループを作成する
- 特権アクセスを有効にする
- 承認ポリシーを作成する

特権アクセス管理を使用すると、組織はゼロの特権で運用し、このような永続的な管理アクセスのために発生する脆弱性に対する防御層を提供できます。 特権アクセスには、関連付けられた承認ポリシーが定義されているタスクを実行する承認が必要です。 承認ポリシーに含まれるタスクを実行する必要があるユーザーは、アクセス承認を要求して付与する必要があります。

特権アクセス管理を有効にするには、「Configure [privileged access management」を参照してください](/office365/securitycompliance/privileged-access-management-configuration)。

詳細については [、「Privileged access management」を参照してください](/office365/securitycompliance/privileged-access-management-overview)。

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>セキュリティ情報とイベント管理 (SIEM) ソフトウェアをMicrosoft 365する

サーバー上で実行される SIEM ソフトウェアは、アプリケーションとネットワーク ハードウェアによって作成されたセキュリティアラートとイベントのリアルタイム分析を実行します。 SIEM サーバーが分析およびレポート機能にMicrosoft 365のセキュリティ 通知とイベントを含めるには、Azure サーバーを SEIM AD統合します。 「[概要」を参照Azure Log Integration。](/azure/security/security-azure-log-integration-overview)

## <a name="next-step"></a>次の手順

サブスクリプションの ID を設定する場合Microsoft 365を参照してください。

- [クラウド専用 ID を](cloud-only-identities.md) 使用している場合のクラウド専用 ID
- [ハイブリッド ID を使用している場合](prepare-for-directory-synchronization.md) は、ディレクトリ同期の準備を行う

  
## <a name="see-also"></a>関連項目

[Microsoft 365のロードマップ](/office365/securitycompliance/security-roadmap)