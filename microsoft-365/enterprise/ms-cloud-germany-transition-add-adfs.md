---
title: ADから移行するための FS 移行手順の詳細
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Microsoft Cloud Deutschland からの移行AD Active Directory フェデレーション サービス (FS) の移行手順について説明します。'
ms.openlocfilehash: bc71c731dd98dd859e7e19065c4c39fc041a530804b28ed5559ab1ac4a84660a
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53885185"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>ADから移行するための FS 移行手順の詳細

この構成変更は、フェーズ 2 が開始される前にいつでも適用する必要があります。
フェーズ 2 が完了すると、構成の変更が機能し、次のようなグローバル Office 365経由でサインインできます `https://admin.microsoft.com` 。 フェーズ 2 より前に構成変更を実装する場合、Office 365 Global エンドポイントはまだ動作しませんが、新しい証明書利用者信頼は Active Directory フェデレーション サービス (AD FS) 構成の一部です。

Active Directory フェデレーション サービス (AD FS) でフェデレーション認証を使用しているお客様は、移行中にオンプレミスの Active Directory ドメイン サービス (AD DS) を使用するすべての認証に使用される発行者 URI を変更する必要があります。 発行者 URI を変更すると、ドメイン内のユーザーの認証エラーが発生します。 発行者 URI は、FS またはドメインAD管理からフェデレーションに変換される場合、またはその逆に直接変更できます。 移行された Azure のフェデレーション ドメインを追加、削除、または変換ADすることをお勧めします。 発行者 URI は、移行が完全に完了した後で変更できます。

Microsoft Cloud Deutschland からの移行AD FS ファームを準備するには、次の手順を実行します。

1. 次の手順AD、既存の Microsoft Cloud Deutschland 証明書利用者信頼を含む FS 設定を [バックアップします](#backup)。 バックアップに **MicrosoftCloudDeutschlandOnly** という名前を付け、Microsoft Cloud Deutschland テナント情報のみを持つ必要があります。

   > [!NOTE]
   > バックアップには、Microsoft Cloud Deutschland の既存の証明書利用者信頼Office 365が含まれるだけでなく、それぞれの FS ファームに存在する他のすべての証明書利用者信頼ADされます。

2. MicrosoftCloudDeutschlandOnly バックアップを使用して復元をテストします。FS ファームAD Microsoft Cloud Deutschland のみとして動作し続ける必要があります。

FS バックアップを完了してテストしたらAD手順を実行して、ADFS 構成に新しい証明書利用者信頼を追加します。

1. [AD FS] 管理コンソールを開きます。

2. ADFS 管理コンソールの左側のウィンドウで、[証明書利用者の信頼] **メニューに移動** します。

3. 右側のウィンドウで、[証明書利用者 **信頼の追加]を選択します。**

4. 証明書 **利用者信頼** の追加 **ウィザードの [** ようこそ] ページで [スタート] を選択します。

5. [データ **ソースの選択] ページ** で、[オンラインまたはローカル ネットワークで発行された証明書利用者に関するデータのインポート **] を選択します**。 フェデレーション **メタデータ アドレス (ホスト名または URL)** の値をに設定する必要があります `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。 **[次へ]** をクリックします。

6. [表示 **名の指定] ページ** で、Id プラットフォーム **WorldWide などの表示Microsoft Office 365入力します**。 **[次へ]** をクリックします。

7. ADFS を使用している場合Windows Server 2012ウィザード ページの [多要素認証を今すぐ構成する **] で**、認証要件に応じて適切な選択肢を選択します。 既定に固執する場合は、[この証明書利用者信頼の多要素認証設定をこの時点で構成しない] **を選択します**。 必要に応じ、後でこの設定を変更できます。

8. [AD FS 2012: 発行承認ルールの選択]で、[すべてのユーザーにこの証明書利用者へのアクセスを許可する] を選択し、[次へ] をクリック **します**。

9. [AD FS 2016 および AD FS 2019:  [アクセス制御ポリシーの選択] ページで、適切なアクセス制御ポリシーを選択し、[次へ] をクリック **します**。 選択されていない場合、証明書利用者信頼は **機能** しません。

10. [ **信頼の準備** 完了] **ページの [次へ] をクリック** して、ウィザードを完了します。

11. [完了 **] ページで** [ **閉じる] をクリック** します。

ウィザードを閉じると、証明書利用者信頼とグローバル サービスOffice 365証明書利用者信頼が確立されます。 ただし、発行変換ルールはまだ構成されていません。

FS ヘルプを [ADして、](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 正しい発行変換ルールを生成できます。 AD FS ヘルプで作成された生成されたクレーム ルールは、AD FS 管理コンソールまたは PowerShell を使用して手動で追加できます。 AD FS ヘルプは、実行する必要がある必要がある PowerShell スクリプトを生成します。  

> [!NOTE]
> [AD FS ヘルプは](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 、製品に含む標準の発行変換ルールを生成します。 ただし、カスタム発行変換ルールが Microsoft Cloud Deutschland 証明書利用者信頼 (カスタム発行者 URI、非標準不変の ID、その他のカスタマイズなど) に適用されている場合、AD FS ヘルプによって生成されるルールは、Microsoft Cloud Deutschland 証明書利用者信頼に対して現在適用されているカスタム ロジックに適合する方法で変更する必要があります。 これらのカスタマイズが AD FS ヘルプを介して生成されたルールに統合されていない場合 [、Microsoft Office 365](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) **Identity Platform WorldWide** への認証は、フェデレーション ID では機能しない可能性が高い。

1. FS **ヘルプで** クレーム [AD実行](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)し、スクリプトの右上隅にある [コピー]オプションを使用して PowerShell スクリプトをコピーします。

2. AD FS ファームで Power AD Shell スクリプトを実行してグローバル証明書利用者信頼を生成する方法については、「AD [FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) ヘルプ」で説明されている手順に従います。 スクリプトを実行する前に、生成されたスクリプトの次のコード行を次のように置き換えます。

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. 2 つの証明書利用者Ttrustsが存在するを確認します。1 つは Microsoft Cloud Deutschland 用、もう 1 つはグローバル Office 365サービス用です。 次のコマンドをチェックに活用できます。 2 つの行と、それぞれの名前と識別子を返す必要があります。

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. 次の手順を使用して、両方の証明書利用者信頼を含む完全な移行構成 [をバックアップします](#backup)。 **MicrosoftCloudDeutschlandAndWorldwide という名前で保存します**。

5. テナントの移行中に、サポートされているさまざまな移行手順で、AD FS 認証が Microsoft Cloud Deutschland および Microsoft Global クラウドで動作しているのを定期的に確認します。

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS 障害復旧 (WID データベース)

障害時にAD FS ファームを復元するにはAD [FS Rapid Restore Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) を活用する必要があります。 したがって、ツールをダウンロードし、移行の開始前にバックアップを作成して安全に保存する必要があります。 この例では、WID データベースで実行されているファームをバックアップするために、次のコマンドを実行しています。

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>FS ファームADバックアップする

1. FS サーバー AD FS ラピッド 復元ツールをインストールADします。

2. このコマンドを使用して、PowerShell セッションでモジュールをインポートします。

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. バックアップ コマンドを実行します。

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. バックアップを目的の宛先に安全に保存します。

### <a name="restore-an-ad-fs-farm"></a>FS ファームAD復元する

ファームが完全に失敗し、古いファームに戻る方法がない場合は、次の手順を実行します。 

1. 以前に生成され保存されたバックアップを FS サーバーの新しいプライマリ AD移動します。

2. 次の `Restore-ADFS` PowerShell コマンドを実行します。 必要に応じて、事前AD FS SSL 証明書をインポートします。

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. 新しい DNS レコードまたはロード バランサーを FS サーバーの新しいADポイントします。

## <a name="more-information"></a>詳細

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

切り替えの移動:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の作業前](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移行プログラム情報](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams へのアップグレードを開始する](/microsoftteams/upgrade-start-here)
