---
title: AD Microsoft Cloud Deutschland からの移行に関する FS 移行手順を確認する
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
description: '概要: Microsoft Cloud Deutschland から移行するための Active Directory フェデレーション サービス (AD FS) 移行手順。'
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688667"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>AD Microsoft Cloud Deutschland からの移行に関する FS 移行手順を確認する

Active Directory フェデレーション サービス (AD FS) ファームを Microsoft Cloud Deutschland から移行するには、

1. 以下の手順をAD FF 信頼情報を含む FS 設定を [バックアップします](#backup)。 バックアップに **Microsoft Cloud Deutschland_Only** 名を付け、Microsoft Cloud Deutschland テナント情報のみを含む必要があります。
2. Microsoft Cloud Deutschland_Only バックアップを使用して復元をテストします。AD FS ファームは Microsoft Cloud Deutschland としてのみ動作する必要があります。
3. FS および 365 サービスから新AD **証明書利用者> Office作成します**。
4. FS **管理コンソールの [** 証明書利用者信頼] AD、[証明書利用者信頼の追加 **] を選択します**。
5. 証明書 **利用者信頼** の **追加ウィザードのウェルカム** ページで [次へ] を選択します。
6. [データ ソース **の選択]** ページで、[オンラインまたはローカル ネットワークで発行された証明書利用者に関するデータ **のインポート] を選択します**。 フェデレーション **メタデータ アドレス (ホスト名または URL)** の値が設定されます `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。 **[次へ]** をクリックします。
7. [データ **ソースの選択] ページ** で、表示名を入力します。 Microsoft では **、Microsoft Office 365 Identity Platform WorldWide を使用する方法をお勧めします**。 **[次へ]** をクリックします。
8. [**今すぐ多** 要素認証を構成しますか **?]** 、[発行承認規則]、および [信頼の追加の準備完了] ページの [次へ **] をクリック** します。
9. [完了 **] ページ** で [閉じる] **をクリック** します。

ウィザードを閉じると、証明書利用者信頼が Office 365 サービス eSTS に確立されます。 ただし、発行変換ルールは確立されません。

適切な発行変換 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) ヘルプを使用して生成できます。 AD FS ヘルプで作成された生成された要求ルールは、AD FS 管理コンソールまたは PowerShell を使用して手動で追加できます。 AD FS ヘルプでは、実行する必要がある必要がある PowerShell スクリプトが生成されます。  

1. AD  FS ヘルプで要求の生成を実行し、スクリプトの右上隅にある [コピー]オプションを使用して PowerShell クレーム変換スクリプトをコピーします。
2. 生成された PowerShell を次の場所に貼り付けます。

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  完成したスクリプトを実行します。
4.  2 つの証明書利用者信頼が存在すること確認します。1 つは世界中向け、もう 1 つは BF 用です。
5.  以下の手順を使用して信頼 [をバックアップします](#backup)。 **FFAndWorldwide という名前で保存します**。
6.  バックエンドの移行を完了し、移行プロセスAD FS が引き続き動作する必要があります。

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS 障害復旧 (WID データベース)

障害時に AD FS ファームを復元 [AD FS 迅速復元ツール](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) を利用する必要があります。 したがって、ツールをダウンロードし、移行の開始前にバックアップを作成して安全に保存する必要があります。 この例 (TAT 環境) では、次のコマンドを実行してファームをバックアップしています。

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>AD FS ファームをバックアップする

1. プライマリ AD FS サーバーに AD FS Rapid Restore Tool をインストールします。
2. 次のコマンドを使用して、PowerShell セッションでモジュールをインポートします。

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. バックアップ コマンドを実行します。

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. 目的のバックアップ先にバックアップを安全に保存します。 

### <a name="restore-an-ad-fs-farm"></a>AD FS ファームを復元する

ファームが完全に失敗し、古いファームに戻る方法がない場合は、次の操作を行います。 

1. 以前に生成および保存したバックアップを、FS サーバーの新しいプライマリ ADに移動します。
2. 次の `Restore-ADFS` PowerShell コマンドを実行します。 必要に応じて、事前に AD FS SSL 証明書をインポートします。

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. 新しい DNS レコードまたはロード バランサーが、新しい FS サーバー ADポイントします。

## <a name="more-information"></a>詳細

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

移行を進む:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [追加の作業前作業](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-add-devices.md)[デバイス](ms-cloud-germany-transition-azure-ad.md)、[エクスペリエンス、および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
