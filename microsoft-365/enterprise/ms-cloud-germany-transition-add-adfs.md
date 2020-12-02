---
title: Microsoft クラウドの移行に関する AD FS 移行手順
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
description: '概要: Microsoft クラウドの移行のための Active Directory フェデレーションサービス (AD FS) の移行手順。'
ms.openlocfilehash: 175734851c2838eb2e224a9afb57a600d4ed9523
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49554817"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft クラウドの移行に関する AD FS 移行手順

Active Directory フェデレーションサービス (AD FS) ファームを Microsoft Cloud Deut上陸陸から移行するには、次のようにします。

1. [次の手順に従っ](#backup)て、FF 信頼情報を含む AD FS 設定をバックアップします。 Microsoft Cloud Deut上陸ランドテナント情報のみが含まれていることを示すために、バックアップ **Microsoft cloud Deutschland_Only** に名前を指定します。
2. 「Microsoft Cloud Deutschland_Only のバックアップを使用して復元をテストする」では、AD FS ファームは、Microsoft Cloud Deut上陸陸のみを引き続き運用する必要があります。
3. **AD FS > Office 365 サービス** から新しい証明書利用者信頼を作成します。
4. AD FS 管理コンソールの **証明書利用者信頼** で、[ **証明書利用者信頼の追加**] を選択します。
5. 証明書利用者信頼の追加ウィザードの [**ようこそ**] ページで、[**次へ**] を選択します。
6. [ **データソースの選択** ] ページで、[ **証明書利用者が公開したオンラインまたはローカルネットワークに関するデータをインポート** する] を選択します。 **フェデレーションメタデータのアドレス (ホスト名または URL)** 値はに設定され `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` ます。 [**次へ**] をクリックします。
7. [ **データソースの選択** ] ページで、表示名を入力します。 Microsoft は、 **世界中の Microsoft Office 365 Id プラットフォーム** をお勧めします。 [**次へ**] をクリックします。
8. [**多要素認証を構成しますか?**] で [**次へ**] をクリックし、[**発行の承認規則**] を選択して、**信頼ページを追加する準備ができ** ました。
9. [**完了**] ページで [**閉じる**] をクリックします。

ウィザードを閉じると、Office 365 services Est への証明書利用者の信頼が確立されます。 ただし、発行変換ルールは確立されません。

[AD FS ヘルプ](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)を使用して、正しい発行変換ルールを生成できます。 AD FS ヘルプを使用して作成されたクレームルールは、AD FS 管理コンソールまたは PowerShell を使用して手動で追加できます。 AD FS ヘルプは、実行する必要のある必要な PowerShell スクリプトを生成します。  

1. スクリプトの右上隅にある [**コピー** ] オプションを使用して、AD FS ヘルプで [**クレームの生成**] を実行し、PowerShell クレーム変換スクリプトをコピーします。
2. 生成された PowerShell を次のように貼り付けます。

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  完成したスクリプトを実行します。
4.  2つの証明書利用者信頼が存在することを確認します。1つはワールドワイドで、もう1つは BF 用です。
5.  [次の手順](#backup)を使用して、信頼関係をバックアップします。 「 **Ffandworldwide**」という名前を付けて保存します。
6.  バックエンドの移行を完了し、移行プロセス中に AD FS が依然として機能することを確認します。

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS の障害復旧 (WID データベース)

障害が発生した ad fs ファームを復元するには、 [ラピッド復元ツール](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) を活用する必要があります。 そのため、ツールをダウンロードしてから、移行の開始前に実行する必要があります。バックアップは、作成して安全に保存する必要があります。 この例 (TAT 環境) では、ファームをバックアップするために次のコマンドが実行されています。

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>AD FS ファームをバックアップする

1. プライマリ AD FS サーバーに AD FS ラピッド Restore ツールをインストールします。
2. このコマンドを使用して、PowerShell セッションでモジュールをインポートします。

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. バックアップコマンドを実行します。

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. 目的の場所にバックアップを安全に保存します。 

### <a name="restore-an-ad-fs-farm"></a>AD FS ファームを復元する

ファームが完全に失敗し、古いファームに戻す方法がない場合は、次の手順を実行します。 

1. 以前に生成および保存されたバックアップを新しいプライマリ AD FS サーバーに移動します。
2. 次の `Restore-ADFS` PowerShell コマンドを実行します。 必要に応じて、AD FS SSL 証明書を事前にインポートします。

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. 新しい DNS レコードまたはロードバランサーを新しい AD FS サーバーの場所にします。

## <a name="more-information"></a>詳細情報

はじめに:

- [新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中の顧客の利便性](ms-cloud-germany-transition-experience.md)

遷移を移動します。

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の準備作業](ms-cloud-germany-transition-add-pre-work.md)
- [サービス](ms-cloud-germany-transition-add-general.md)、[デバイス](ms-cloud-germany-transition-add-devices.md)、[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、 [AD FS](ms-cloud-germany-transition-add-adfs.md)の追加情報。

クラウドアプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
