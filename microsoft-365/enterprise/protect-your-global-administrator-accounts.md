---
title: Microsoft 365 グローバル管理者アカウントを保護する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: この記事では、Microsoft 365 サブスクリプションへのグローバル管理者アクセスの保護に関する情報を提供します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9693a8321643539e21ff10f3c624a0558916eb29
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198351"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Microsoft 365 グローバル管理者アカウントを保護する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

情報収集やフィッシング攻撃など、Microsoft 365 サブスクリプションのセキュリティ違反は通常、Microsoft 365 グローバル管理者アカウントの資格情報の侵害により発生します。 クラウドのセキュリティは、お客様と Microsoft 間のパートナーシップに基づくものです。
  
- Microsoft クラウド サービスは信頼とセキュリティの基盤の上に構築されます。 Microsoft が提供するセキュリティ制御と機能は、お客様のデータとアプリケーションの保護に役立ちます。
    
- お客様はご自分のデータと ID を所有しており、それらとオンプレミス リソースのセキュリティ、およびご自分が制御しているクラウド コンポーネントのセキュリティを保護する責任を担っています。
    
Microsoft は、組織を保護するための機能を提供していますが、それらの機能を使用する場合にのみ有効です。 使用しないと、攻撃に対して脆弱になる可能性があります。 グローバル管理者アカウントを保護するために、Microsoft は次の詳細な手順を支援します。
  
1. 専用の Microsoft 365 グローバル管理者アカウントを作成し、必要な場合にのみ使用します。
    
2. 専用の Microsoft 365 グローバル管理者アカウントに対して多要素認証を構成し、最も強力な形式の第 2 認証を使用します。
    
> [!Note]
> この記事は、グローバル管理者アカウントに重点を置いていますが、サブスクリプションのデータへの広範なアクセス権限を持つ追加のアカウント (電子情報開示管理者アカウント、セキュリティ アカウント、コンプライアンス アカウントなど) も同じように保護する必要があるかどうかを検討する必要があります。 <br > グローバル管理者アカウントは、ライセンスを追加せずに作成できます。
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>手順 1. 専用の Microsoft 365 グローバル管理者アカウントを作成し、必要な場合にのみ使用します

グローバル管理者特権を必要とする、ユーザー アカウントへのロールの割り当てなどの管理タスクは比較的少数です。 そのため、グローバル管理者ロールが割り当てられている一般的なユーザー アカウントを使用するのではなく、次の手順を実行してください。
  
1. グローバル管理者ロールが割り当てられているユーザー アカウント セットを判別します。 これは、Microsoft 365 管理センターで、または次のAzure Active (Azure AD) Directory PowerShell for Graph コマンドを使用して実行できます。
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. グローバル管理者ロールが割り当てられているユーザー アカウントを使用して、Microsoft 365 サブスクリプションにサインインします。
    
3. 最大 4 つの専用グローバル管理者ユーザー アカウントを作成します。 **長さが 12 文字以上の強力なパスワードを使用します。** 詳細については、「[強力なパスワードを作成する](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password)」を参照してください。 新しいアカウントのパスワードを安全な場所に保存します。 
    
4. 新しい専用のグローバル管理者ユーザー アカウントごとにグローバル管理者ロールを割り当てます。
    
5. Microsoft 365 からサインアウトします。
    
6. 新しい専用のグローバル管理者ユーザー アカウントのいずれかでサインインします。
    
7. 手順 1 で判別した、グローバル管理者ロールが割り当てられている既存のユーザー アカウントごとに、次の操作を実行します。
    
  - グローバル管理者ロールを削除します。
    
  - そのユーザーの職務と職責に適したアカウントに管理者ロールを割り当てます。 Microsoft 365 のさまざまな管理者ロールの詳細については、「[管理者ロールについて](/office365/admin/add-users/about-admin-roles)」を参照してください。
    
8. Microsoft 365 からサインアウトします。
    
次のような結果が表示されます。
  
- グローバル管理者ロールを持つ、サブスクリプションのユーザー アカウントのみが、新しい専用のグローバル管理者アカウント セットとなります。 次の PowerShell コマンドでこれを確認します。
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- サブスクリプションを管理するその他の通常のユーザー アカウントには、各自の職務に関連する管理ロールが割り当てられています。
    
これ以降は、グローバル管理者特権を必要とするタスクの場合にのみ、専用のグローバル管理者アカウントでサインインすることになります。 他のすべての Microsoft 365 の管理は、他の管理ロールをユーザー アカウントに割り当てて行う必要があります。
  
> [!NOTE]
> これには、日常のユーザー アカウントとしてサインアウトし、専用のグローバル管理者アカウントでサインインするための追加の手順が必要です。 ただし、これはグローバル管理者の操作でときどき実行する必要があります。 グローバル管理者アカウントが侵害された場合、Microsoft 365 サブスクリプションの復元にさらに多くの手順が必要になることを重視してください。
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>手順 2.  専用の Microsoft 365 グローバル管理者アカウントの多要素認証を構成する

多要素認証 (MFA) には、アカウント名とパスワード以外の追加情報が必要です。 Microsoft 365 は、次の追加の検証方法をサポートしています。
  
- Microsoft Authenticator アプリ

- 電話
    
- テキスト メッセージを介して送信されるランダムに生成された確認コード
    
- スマート カード (仮想または物理)
    
- 生体認証デバイス
    
>[!Note]
>アメリカ国立標準技術研究所 (NIST) の標準に準拠する必要がある組織では、電話またはテキスト メッセージベースの追加の検証方法の使用が制限されています。 詳細については、[ここ](https://pages.nist.gov/800-63-FAQ/#q-b01)をクリックしてください。
>

クラウドにのみ保存されているユーザーアカウント (クラウドのみの ID モデル) を使用している中小企業の場合は、専用のグローバル管理者アカウントごとにスマートフォンに送信される電話またはテキスト メッセージ確認コードを使用して MFA を構成するように [MFA を設定](/office365/admin/security-and-compliance/set-up-multi-factor-authentication)します。
    
Microsoft 365 ハイブリッド ID モデルを使用している大規模な組織の場合は、より多くの検証オプションがあります。 より強力な二次認証方法のためのセキュリティ インフラストラクチャがすでに整っている場合は、[MFA を設定](../admin/security-and-compliance/set-up-multi-factor-authentication.md)し、適切な検証方法のために各専用グローバル管理者アカウントを構成します。
  
必要なより強力な検証方法のセキュリティ インフラストラクチャが整っておらず、Microsoft 365 MFA で機能していない場合は、Microsoft Authenticator アプリ、電話、または送信されたテキスト メッセージ検証コードを使用して、MFA で専用のグローバル管理者アカウントを構成することを強くお勧めします。 暫定的なセキュリティ対策として、グローバル管理者アカウント用のスマートフォンに接続します。 MFA で保護が強化されていない専用のグローバル管理者アカウントをそのまま使用しないでください。
  
詳細については、「[Microsoft 365 の MFA](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)」を参照してください。
  
MFA と PowerShell を使用して Microsoft 365 サービスに接続する場合は、こちらの記事を参照してください。

- [ユーザーアカウント、グループ、およびライセンス用の PowerShell for Microsoft 365](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](/microsoftteams/teams-powershell-install)
- [Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>企業組織のための追加の保護

以下の追加の方法を使用して、グローバル管理者のアカウントと、このアカウントを使用して実行する構成とが可能な限りセキュリティで保護されるようにします。
  
### <a name="privileged-access-workstation"></a>特権アクセス ワークステーション (PAW)

高い権限を持つタスクの実行が、可能な限りセキュリティで保護されるようにするには、特権アクセス ワークステーション (PAW) を使用します。 PAW とは、グローバル管理者アカウントが必要とされる Microsoft 365 の構成など、機密性の高い構成タスクでのみ使用される専用のコンピューターです。 このコンピューターではインターネットの閲覧やメールを日常行わないので、インターネットの攻撃や脅威から適切に保護されます。
  
PAWの設定方法については、[https://aka.ms/cyberpaw](/security/compass/privileged-access-devices)を参照してください。

Azure AD テナントと管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。

サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](/azure/active-directory/admin-roles-best-practices)」を参照してください。

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

グローバル管理者アカウントにグローバル管理者の役割を永続的に割り当てるのではなく、Azure AD Privileged Identity Management (PIM) を使用して、必要なときに、オンデマンドのジャストインタイム割り当てを有効にすることができます。
  
グローバル管理者アカウントは、永続的な管理者ではなく適格な管理者になります。 グローバル管理者ロールは、誰かが必要とするまで非アクティブとなります。 ライセンス認証プロセスを実行すると、事前に設定された期間、グローバル管理者ロールがグローバル管理者アカウントに追加されます。 期限を過ぎると、PIM によってグローバル管理者アカウントからグローバル管理者ロールが削除されます。
  
PIM と、このプロセスを使用することにより、グローバル管理者アカウントが、悪意のあるユーザーによる攻撃と使用に対して脆弱になる時間が大幅に短くなります。

PIM は、Microsoft 365 E5 に含まれている Azure Active Directory Premium P2 で使用できます。 または、管理者アカウントの Azure Active Directory Premium P2 ライセンスを個別に購入できます。
  
詳細については、「[Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)」を参照してください。
  

### <a name="privileged-access-management"></a>特権アクセス管理

特権アクセス管理は、テナントでのタスクベースのアクティビティに対して Just-In-Time アクセスを指定するポリシーを構成することで有効になります。これは、機密性の高いデータへの継続的なアクセスや重要な構成設定へのアクセスに、既存の特権管理者アカウントが使用される可能性のある侵害から組織を保護するために役立ちます。たとえば、テナント内の組織のメールボックス設定にアクセスして変更する際には、明示的な承認が必要になる特権アクセス管理ポリシーを構成できます。

この手順では、テナントの特権アクセス管理を有効にして、組織のデータおよび構成設定へのタスクベースのアクセスに対するセキュリティを強化する特権アクセスポリシーを構成します。組織の特権アクセスは、次の 3 つの基本的な手順で開始します。

- 承認者のグループを作成する
- 特権アクセスを有効にする
- 承認ポリシーを作成する

特権アクセス管理により、組織は永続的な特権なしで運用でき、そのような永続的な管理アクセスによって発生する脆弱性に対する防御レイヤーを提供できます。 特権アクセスには、関連する承認ポリシーが定義されているタスクを実行するための承認が必要です。 承認ポリシーに含まれるタスクを実行する必要があるユーザーは、アクセス承認を要求して許可する必要があります。

特権アクセス管理を有効にするには、「[特権アクセス管理を構成する](/office365/securitycompliance/privileged-access-management-configuration)」を参照してください。

詳細については、「[特権アクセス管理](/office365/securitycompliance/privileged-access-management-overview)」を参照してください。

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Microsoft 365 ログ記録用のセキュリティ情報とイベント管理 (SIEM)

サーバー上で実行される SIEM ソフトウェアは、アプリケーションとネットワーク ハードウェアによって作成されたセキュリティ アラートとイベントのリアルタイム分析を実行します。 SIEM サーバーが Microsoft 365 のセキュリティ アラートとイベントを分析およびレポート機能に含めることができるようにするには、Azure AD を SEIM に統合します。 「[Azure Log Integration の概要](/azure/security/security-azure-log-integration-overview)」を参照してください。

## <a name="next-step"></a>次の手順

Microsoft 365 サブスクリプションの ID を設定する場合は、以下を参照してください。

- クラウド専用の ID を使用している場合は、「[クラウド専用の ID](cloud-only-identities.md)」
- ハイブリッドIDを使用している場合は、「[ディレクトリ同期を準備する](prepare-for-directory-synchronization.md)」

  
## <a name="see-also"></a>関連項目

[Microsoft 365 セキュリティ センター ロードマップ](/office365/securitycompliance/security-roadmap)