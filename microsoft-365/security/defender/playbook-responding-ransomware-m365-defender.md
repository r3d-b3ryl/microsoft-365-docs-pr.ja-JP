---
title: ランサムウェア攻撃への対応
description: この記事では、ランサムウェア攻撃に対応するための汎用プレイブックを提供します。
search.appverid: MET150
author: nic-name
ms.author: noriordan
manager: dolmont
audience: ITPro
ms.topic: article
ms.date: 05/30/2022
ms.service: microsoft-365-security
ms.subservice: m365d
ms.localizationpriority: medium
ms.collection: M365-security-compliance
f1.keywords: NOCSH
ms.openlocfilehash: a3e0cc3c79829ad5a13a6da29858d6d7c60cf322
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67469802"
---
# <a name="responding-to-ransomware-attacks"></a>ランサムウェア攻撃への対応

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

ランサムウェア攻撃を受けている可能性がある場合、または現在ランサムウェア攻撃を受けている可能性がある場合は、インシデント対応チームとの安全な通信を直ちに確立します。 攻撃を中断し、被害を軽減するために、次の対応フェーズを実行できます。

* 調査と包含
* 根絶と回復

この記事では、ランサムウェア攻撃に対応するための汎用プレイブックを提供します。 この記事で説明されている手順とタスクを、独自のセキュリティ操作プレイブックに適応することを検討してください。
注: ランサムウェア攻撃の防止については、「 [ランサムウェアや強要から迅速に保護する](/security/compass/protect-against-ransomware)」を参照してください。

## <a name="containment"></a>コンテインメント

包含と調査は、可能な限り同時に行う必要があります。ただし、調査する時間を増やすために、コンテインメントを迅速に実現することに重点を置く必要があります。 これらの手順は、攻撃の範囲を特定し、影響を受けるエンティティ (ユーザー アカウントやデバイスなど) のみに分離するのに役立ちます。

### <a name="step-1-assess-the-scope-of-the-incident"></a>手順 1: インシデントの範囲を評価する

この質問とタスクの一覧を実行して、攻撃の範囲を検出します。 Microsoft 365 Defenderは、インシデント対応の評価を支援するために、影響を受ける資産または危険にさらされているすべての資産の統合ビューを提供できます。 [Microsoft 365 Defenderを使用したインシデント対応に関する](incidents-overview.md)Microsoft 365 Defenderを参照してください。 アラートとインシデントの証拠一覧を使用して、次の情報を確認できます。

* 侵害される可能性があるユーザー アカウントはどれですか?
  * ペイロードの配信に使用されたアカウントはどれですか?
* [どのオンボード](../defender-endpoint/investigate-machines.md)デバイスと[検出されたデバイスが](../defender-endpoint/device-discovery.md)影響を受け、どのように影響しますか?
  * 発信元デバイス
  * 影響を受けたデバイス
  * 疑わしいデバイス
* インシデントに関連付けられているすべてのネットワーク通信を識別します。
* 影響を受けるアプリケーションはどれですか?
* どのペイロードが分散されましたか?
* 攻撃者は侵害されたデバイスとどのように通信していますか? (ネットワーク保護を [有効にする](../defender-endpoint/enable-network-protection.md)必要があります):
  * [インジケーター ページ](../defender-endpoint/indicator-ip-domain.md#create-indicators-for-ips-and-urlsdomains)に移動して、IP と URL のブロックを追加します (その情報がある場合)。
* ペイロード配信メディアは何でしたか?

### <a name="step-2-preserve-existing-systems"></a>手順 2: 既存のシステムを保持する

既存のシステムを攻撃から保護するために、次のタスクと質問の一覧を実行します。

* オンライン バックアップがある場合は、攻撃が含まれていると確信できるまでネットワークからバックアップ システムを切断することを検討してください。[ランサムウェアから保護するためのバックアップと復元の計画|Microsoft Docs](/security/compass/backup-plan-to-protect-against-ransomware)。
* 差し迫ったアクティブなランサムウェアの展開が発生している場合、または予期している場合は、次の手順に従います。
  * 攻撃の一部と思われる[特権アカウントとローカル アカウントを一時停止](/investigate-users.md)します。 これは、Microsoft 365 Defender ポータルのインシデントのプロパティの [**ユーザー**] タブから行うことができます。
  * [すべてのリモート ログオン セッションを停止します](/defender-for-identity/playbook-domain-dominance)。
  * 侵害されたユーザー アカウントのパスワードをリセットし、侵害されたユーザー アカウントのユーザーにもう一度サインインするように要求します。
  * 侵害される可能性があるユーザー アカウントでも同じ操作を行います。
  * 共有ローカル アカウントが侵害された場合は、IT 管理者に、公開されているすべてのデバイスでパスワード変更を適用するのに役立ちます。 Kusto クエリの例:

```kusto
DeviceLogonEvents | where DeviceName  contains (AccountDomain) | take 10 
```

* まだ分離されておらず、重要なインフラストラクチャの一部ではないデバイスの場合:
  * 侵害されたデバイスをネットワークから分離しますが、シャットダウンしないでください。
  * 発信元デバイスまたはスプレッダー デバイスを特定する場合は、最初にデバイスを分離します。
* 侵害されたシステムを分析用に保持します。

### <a name="step-3-prevent-the-spread"></a>手順 3: 拡散を防止する

この一覧を使用して、攻撃が他のエンティティに拡散しないようにします。

* 攻撃で共有ローカル アカウントが使用されている場合は、 [ローカル アカウントのリモート使用をブロック](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/blocking-remote-use-of-local-accounts/ba-p/701042)することを検討してください。
  * ローカル管理者であるすべてのネットワーク ログオンに対する Kusto クエリ:

```kusto
DeviceLogonEvents
| where IsLocalAdmin == true and AccountDomain == DeviceName
| extend IsLocalLogon = tobool(todynamic(AdditionalFields).IsLocalLogon)
| where IsLocalLogon==false
```

* RDP 以外のログオンに対する Kusto クエリ (ほとんどのネットワークではより現実的):

```kusto
DeviceLogonEvents
| where IsLocalAdmin == true and AccountDomain == DeviceName and LogonType != 'RemoteInteractive'
| extend IsLocalLogon = tobool(todynamic(AdditionalFields).IsLocalLogon)
| where IsLocalLogon==false
```

* 感染しているファイルの検疫とインジケーターの追加。
* ウイルス対策ソリューションが最適な保護状態で構成可能であることを確認します。 Microsoft Defender ウイルス対策の場合、これには次のものが含まれます。
  * [リアルタイム保護](../defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus.md) が有効になっています。
  * [改ざん防止](../defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection.md) が有効になっています。 Microsoft 365 Defender ポータルで、[**設定] > [エンドポイント] > [改ざん防止>高度な機能**] を選択します。
  * [攻撃対象の縮小 (ASR)](../defender-endpoint/enable-attack-surface-reduction.md) ルールが有効になっています。
  * [クラウド保護](../defender-endpoint/enable-attack-surface-reduction.md) が有効になっています。
* Exchange ActiveSyncとOneDrive 同期を無効にします。
  * メールボックスのExchange ActiveSyncを無効にするには、「[Exchange OnlineのユーザーのExchange ActiveSyncを無効にする方法」を](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-exchange-activesync)参照してください。
  * メールボックスへの他の種類のアクセスを無効にするには、次を参照してください。
    * [メールボックスの MAPI を有効または無効にします](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。
    * [ユーザーの POP3 または IMAP4 アクセスを有効または無効にします](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)。
  * OneDrive 同期を一時停止すると、感染する可能性のあるデバイスによってクラウド データが更新されないように保護できます。 詳細については、「 [OneDrive で同期を一時停止および再開する方法](https://support.microsoft.com/office/how-to-pause-and-resume-sync-in-onedrive-2152bfa4-a2a5-4d3a-ace8-92912fb4421e)」を参照してください。
* 影響を受けるシステムに関連するパッチと構成変更を適用します。
* 内部および外部の制御を使用してランサムウェアの通信をブロックします。
* キャッシュされたコンテンツを消去する

## <a name="investigation"></a>調査

このセクションを使用して、攻撃を調査し、対応を計画します。

### <a name="assess-your-current-situation"></a>現在の状況を評価する

* ランサムウェア攻撃を最初に認識した理由は何ですか?
  * IT スタッフが最初の脅威 (バックアップが削除されていることに気付く、ウイルス対策アラート、エンドポイントの検出と応答 (EDR) アラート、疑わしいシステム変更など) を特定した場合、攻撃を阻止するための迅速な決定的な手段 (通常は、この記事で説明した封じ込めアクション) を実行できます。
* インシデントを最初に知った日時は何日ですか?
  * その日にデバイスにインストールされなかったシステム更新プログラムとセキュリティ更新プログラムは何ですか? これは、他のデバイスで対処できるように、どのような脆弱性が利用されたかを理解するために重要です。
  * その日に使用されたユーザー アカウントは何ですか?
  * その日以降に作成された新しいユーザー アカウントは何ですか?
  * インシデントが発生した頃に自動的に開始するために追加されたプログラムは何ですか?
* 攻撃者が現在システムにアクセスしているという兆候はありますか?
  * 異常なアクティビティが発生している侵害された可能性のあるシステムはありますか?
  * 敵対者によって積極的に使用されているように見える侵害された疑いのあるアカウントはありますか?
  * EDR、ファイアウォール、VPN、Web プロキシ、その他のログにアクティブなコマンドアンドコントロール (C2) サーバーの証拠はありますか?

### <a name="identify-the-ransomware-process"></a>ランサムウェア プロセスを特定する

* [高度な捜索](/microsoft-365/security/defender/advanced-hunting-overview.md)を使用して、他のデバイス上のプロセス作成イベントで特定されたプロセスを検索します。

### <a name="look-for-exposed-credentials-in-the-infected-devices"></a>感染したデバイスで公開されている資格情報を探す

* 資格情報が侵害された可能性があるユーザー アカウントの場合は、アカウントのパスワードをリセットし、ユーザーにもう一度サインインを要求します。
* 次の IOA は、横方向の動きを示している可能性があります。

<details>
  <summary>クリックして展開</summary>

* SuspiciousExploratoryCommands
* MLFileBasedAlert
* IfeoDebuggerPersistence
* SuspiciousRemoteFileDropAndExecution
* ExploratoryWindowsCommands
* IoaStickyKeys
* Mimikatz Defender の増幅
* PARINACOTA で使用されるネットワーク スキャン ツール
* DefenderServerAlertMSSQLServer
* SuspiciousLowReputationFileDrop
* SuspiciousServiceExecution
* AdminUserAddition
* MimikatzArtifactsDetector
* Scuba-WdigestEnabledToAccessCredentials
* DefenderMalware
* MLSuspCmdBehavior
* MLSuspiciousRemoteInvocation
* SuspiciousRemoteComponentInvocation
* SuspiciousWmiProcessCreation
* MLCmdBasedWithRemoting
* プロセス アクセス Lsass
* 疑わしい Rundll32 プロセスの実行
* BitsAdmin
* DefenderCobaltStrikeDetection
* DefenderHacktool
* IoaSuspPSCommandline
* Metasploit
* MLSuspToolBehavior
* RegistryQueryForPasswords
* SuspiciousWdavExclusion
* ASEPRegKey
* CobaltStrikeExecutionDetection
* DefenderBackdoor
* DefenderBehaviorSuspiciousActivity
* DefenderMalwareExecuted
* DefenderServerAlertDomainController
* DupTokenPrivilegeEscalationDetector
* FakeWindowsBinary
* IoaMaliciousCmdlets
* LivingOffTheLandBinary
* MicrosoftSignedBinaryAbuse
* MicrosoftSignedBinaryScriptletAbuse
* MLFileBasedWithRemoting
* MLSuspSvchostBehavior
* ReadSensitiveMemory
* RemoteCodeInjection-IREnabled
* Scuba-EchoSeenOverPipeOnLocalhost
* Scuba-SuspiciousWebScriptFileDrop
* odbcconf による疑わしい DLL 登録
* 不審な DPAPI アクティビティ
* 不審な Exchange プロセスの実行
* 疑わしいスケジュールされたタスクの起動
* SuspiciousLdapQueryDetector
* SuspiciousScheduledTaskRegistration
* 信頼されていないアプリケーションが RDP 接続を開く

</details>

### <a name="identify-the-line-of-business-lob-apps-that-are-unavailable-due-to-the-incident"></a>インシデントが原因で利用できない基幹業務 (LOB) アプリを特定する

* アプリには ID が必要ですか?
  * 認証はどのように実行されますか?
  * 証明書やシークレットなどの資格情報はどのように格納され、管理されますか?
* アプリケーション、その構成、およびデータの評価されたバックアップは使用できますか?
* 侵害復旧プロセスを決定します。

## <a name="eradication-and-recovery"></a>根絶と回復

脅威を排除し、破損したリソースを回復するには、次の手順に従います。

### <a name="step-1-verify-your-backups"></a>手順 1: バックアップを確認する

オフライン バックアップがある場合は、おそらく、環境からランサムウェア ペイロード (マルウェア) を削除した後、および Microsoft 365 テナントに不正アクセスがないことを確認した後に、暗号化されたデータを復元できます。

### <a name="step-2-add-indicators"></a>手順 2: インジケーターを追加する

既知の攻撃者通信チャネルをインジケーターとして追加し、ファイアウォール、プロキシ サーバー、エンドポイントでブロックします。

### <a name="step-3-reset-compromised-users"></a>手順 3: 侵害されたユーザーをリセットする

侵害された既知のユーザー アカウントのパスワードをリセットし、新しいサインインが必要です。

* Domain Admins グループのメンバーなど、広範な管理権限を持つ特権アカウントのパスワードをリセットすることを検討してください。
* 攻撃者によってユーザー アカウントが作成された可能性がある場合は、アカウントを無効にします。 インシデントのセキュリティ フォレンジックを実行する計画がない場合を除き、アカウントを削除しないでください。

### <a name="step-4-isolate-attacker-control-points"></a>手順 4: 攻撃者の制御ポイントを分離する

企業内の既知の攻撃者制御ポイントをインターネットから分離します。

### <a name="step-5-remove-malware"></a>手順 5: マルウェアを削除する

影響を受けるデバイスからマルウェアを削除します。

* ランサムウェアに関連付けられているペイロードを検出して削除するには、疑わしいすべてのコンピューターとデバイスで完全な現在のウイルス対策スキャンを実行します。
* データを同期するデバイスや、マップされたネットワーク ドライブのターゲットをスキャンすることを忘れないでください。

### <a name="step-6-recover-files-on-a-cleaned-device"></a>手順 6: クリーニングされたデバイス上のファイルを回復する

クリーニングされたデバイス上のファイルを回復します。

* Windows 7 では、Windows 11、Windows 10、Windows 8.1、および System Protection で[ファイル履歴](https://support.microsoft.com/help/17128)を使用して、ローカル ファイルとフォルダーの回復を試みることができます。

### <a name="step-7-recover-files-in-onedrive-for-business"></a>手順 7: OneDrive for Business でファイルを回復する

OneDrive for Business内のファイルを回復します。

* OneDrive for Businessファイルの復元では、過去 30 日以内に OneDrive 全体を以前の時点に復元できます。 詳細については、「[OneDrive を復元する](https://support.microsoft.com/office/restore-your-onedrive-fa231298-759d-41cf-bcd0-25ac53eb8a15)」を参照してください。

### <a name="step-8-recover-deleted-email"></a>手順 8: 削除されたメールを回復する

削除されたメールを回復します。

* ランサムウェアによってメールボックス内のすべてのメールが削除されたというまれなケースでは、削除されたアイテムを回復できます。 [Exchange Onlineのユーザーのメールボックスで削除されたメッセージを回復する](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)方法に関する記事を参照してください。

### <a name="step-9-re-enable-exchange-activesync-and-onedrive-sync"></a>手順 9: Exchange ActiveSyncとOneDrive 同期を再度有効にする

* コンピューターとデバイスをクリーニングしてデータを回復したら、包含の手順 3 で以前に無効にしたExchange ActiveSyncとOneDrive 同期を再度有効にすることができます。
