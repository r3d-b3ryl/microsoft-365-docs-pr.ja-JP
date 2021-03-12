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
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727469"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>ADから移行するための FS 移行手順の詳細

この構成変更は、フェーズ 4 が開始される前にいつでも適用できます。
フェーズ 2 が完了すると、構成の変更が機能し、次のような 365 グローバル Officeにサインインできます `https://portal.office.com` 。 フェーズ 2 より前に構成変更を実装する場合、Office 365 グローバル エンドポイントはまだ動作しませんが、新しい証明書利用者信頼は Active Directory フェデレーション サービス (AD FS) 構成の一部です。

Microsoft Cloud Deutschland AD FS ファームを移行するには、次の方法を実行します。

1. FF 信頼情報を含AD FS 設定を次の手順で [バックアップします](#backup)。 バックアップに **Microsoft Cloud ドメインDeutschland_Only** 名を付け、Microsoft Cloud Deutschland テナント情報のみを持つ必要があります。
2. Microsoft Cloud Deutschland_Onlyバックアップを使用して復元をテストしますAD FS ファームは引き続き Microsoft Cloud Deutschland としてのみ動作する必要があります。

FS バックアップを完了してテストしたらAD手順を実行して、ADFS 構成に新しい証明書利用者信頼を追加します。

1. FS 管理コンソールAD開く
2. ADFS 管理コンソールの左側のウィンドウで **、[ADFS]**、[信頼関係] の順に展開し、[証明書利用者 **の信頼] を展開します。**
3. 右側のウィンドウで、[証明書利用者 **信頼の追加]を選択します。**
4. 証明書 **利用者信頼** の追加 **ウィザードの [** ようこそ] ページで [次へ] を選択します。
5. [データ **ソースの選択] ページ** で、[オンラインまたはローカル ネットワークで発行された証明書利用者に関するデータのインポート **] を選択します**。 フェデレーション **メタデータ アドレス (ホスト名または URL)** の値をに設定する必要があります `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。 **[次へ]** をクリックします。
6. [データ **ソースの選択]** ページで、365 Identity Platform WorldWide などのMicrosoft Office **を入力します**。 **[次へ]** をクリックします。
7. [多要素認証を今すぐ構成する **]** ウィザード ページで、認証要件に応じて適切な選択肢を選択します。 既定に固執する場合は、[この証明書利用者信頼の多要素認証設定をこの時点で構成しない] **を選択します**。 必要に応じ、後でこの設定を変更できます。
8. [発行承認 **ルールの選択]** で、[すべてのユーザーにこの証明書利用者へのアクセスを許可する] をオンにし、[次へ] をクリック **します**。
9. [ **信頼の準備** 完了] **ページの [次へ] をクリック** して、ウィザードを完了します。
10. [完了 **] ページで** [ **閉じる] をクリック** します。

ウィザードを閉じると、証明書利用者信頼と 365 グローバル Officeサービスが確立されます。 ただし、発行変換ルールはまだ構成されていません。

FS ヘルプを [ADして、](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 正しい発行変換ルールを生成できます。 AD FS ヘルプで作成された生成されたクレーム ルールは、AD FS 管理コンソールまたは PowerShell を使用して手動で追加できます。 AD FS ヘルプは、実行する必要がある必要がある PowerShell スクリプトを生成します。  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. FS **ヘルプで** クレームAD実行し、スクリプトの右上隅にある [コピー] オプションを使用してPowerShell クレーム変換スクリプトをコピーします。
2. 優先するテキスト エディターを開き、PowerShell スクリプトを新しいテキスト ウィンドウに貼り付けます。
3. 手順 2 から貼り付けスクリプトの末尾に次の PowerShell 行を追加する
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. PowerShell スクリプトを安全に実行します。
5. 2 つの証明書利用者信頼が存在すること。1 つは Microsoft Cloud Deutschland 用、もう 1 つは Office 365 Global サービス用です。
6. これらの手順を使用して信頼 [をバックアップします](#backup)。 **FFAndWorldwide という名前で保存します**。
7. バックエンドの移行を完了し、移行AD FS が引き続き動作します。

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS 障害復旧 (WID データベース)

障害時にAD FS ファームを復元するにはAD [FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) を活用する必要があります。 したがって、ツールをダウンロードし、移行の開始前にバックアップを作成して安全に保存する必要があります。 この例 (TAT 環境) では、ファームをバックアップするために次のコマンドが実行されています。

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

## <a name="more-information"></a>詳細情報

はじめに:

- [新しいドイツのデータセンター地域Office 365 サービスへの Microsoft Cloud Deutschland からの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

切り替えの移動:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の作業前](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
