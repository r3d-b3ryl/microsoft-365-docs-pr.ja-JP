---
title: 攻撃表面の縮小に関するよく寄せられる質問 (FAQ)
description: Microsoft Defender for Endpoint の攻撃表面縮小ルールに関するよく寄せられる質問に対する回答を見つける。
keywords: 攻撃表面の縮小ルール、asr、hips、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、エンドポイント用 microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3ca429ca1fea125450fdbb8d1f3a0e3a745513d8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245698"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>攻撃表面の縮小に関するよく寄せられる質問 (FAQ)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>攻撃表面の縮小 (ASR) は、攻撃の一部Windows?

ASR はもともと、Microsoft Defender ウイルス対策 バージョン 1709 の Microsoft Defender ウイルス対策 Windows 10 の主要な更新プログラムとして導入されたエクスプロイト ガード機能のスイートの機能でした。 Microsoft Defender ウイルス対策は、マルウェア対策のネイティブ コンポーネントWindows。 ただし、完全な ASR 機能セットは、エンタープライズ ライセンスWindows使用できます。 また、ASR ルールの除外は、ユーザーの除外とは別Microsoft Defender ウイルス対策注意してください。

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>ASR ルールを実行するには、エンタープライズ ライセンスが必要ですか?

ASR ルールと機能の完全なセットは、エンタープライズ ライセンスを使用している場合にのみサポートWindows 10。 限られた数のルールは、エンタープライズ ライセンスなしで動作する場合があります。 必要な情報Microsoft 365 Business、Microsoft Defender ウイルス対策セキュリティ ソリューションとして設定し、PowerShell を使用してルールを有効にしてください。 エンタープライズ ライセンスなしで ASR を使用しても、正式にはサポートされていないので、ASR の完全な機能を使用することはできません。

ライセンスの詳細については、「Windows ライセンス」を参照し[](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5)Windows 10ボリューム ライセンス ガイド[を](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)参照Windows 10。

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>E3 ライセンスを持っている場合、ASR はサポートされていますか?

はい。 ASR は E3 以上Windows Enterpriseサポートされています。 

## <a name="which-features-are-supported-with-an-e5-license"></a>E5 ライセンスでサポートされている機能は何ですか?

E3 でサポートされるルールはすべて、E5 でもサポートされています。

E5 は、Defender for Endpoint とのより大きな統合を追加します。 E5 を使用すると、リアルタイムでアラートを表示し、ルールの除外を微調整し、ASR ルールを構成し、イベント レポートのリストを表示できます。

## <a name="what-are-the-currently-supported-asr-rules"></a>現在サポートされている ASR ルールは何ですか?
ASR は現在、以下のすべてのルールをサポートしています。

## <a name="what-rules-to-enable-all-or-can-i-turn-on-individual-rules"></a>有効にするルール すべて、または個々のルールを有効にできますか?
環境に最適な機能を把握するために、監査モードで ASR ルールを [有効にしてください](audit-windows-defender.md)。 この方法では、組織に与える影響を判断します。 たとえば、業務のライン アプリケーションなどです。

## <a name="how-do-asr-rules-exclusions-work"></a>ASR ルールの除外は、どのように機能しますか?
ASR ルールの場合、除外を 1 つ追加すると、すべての ASR ルールに影響します。
次の 2 つの特定のルールでは、除外はサポートされていません。

|ルールの名前|GUID|ファイル&フォルダーの除外|
|:--|:--|:--|
|JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする|D3E037E1-3EB8-44C8-A917-57927947596D|非サポート|
|WMI イベント サブスクリプションによる永続化のブロック|e6db77e5-3df2-4cf1-b95a-636979351e5b|非サポート|

ASR ルールの除外は、ワイルドカード、パス、および環境変数をサポートします。 ASR ルールでワイルドカードを使用する方法の詳細については、「ファイル拡張子とフォルダーの場所に基づいて除外を構成および検証する [」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus)。

ASR ルールの除外に関する次の項目 (ワイルドカードや env を含む) に注意してください。 変数:

- ASR ルールの除外は、Defender AV の除外とは独立しています
- ワイルドカードを使用してドライブ文字を定義することはできません
- 複数のフォルダーをパスで除外する場合は、\ の複数のインスタンスを使用して、複数の入れ子になったフォルダーを示します \* (たとえば、c:\Folder \* \* \Test)
- Microsoft Endpoint Configuration Manager *ワイルドカード (** または ?) をサポートしていない場合
- ランダムな文字 (自動ファイル生成) を含むファイルを除外する場合は、'?' 記号を使用できます (たとえば、C:\Folder\fileversion?.docx)
- グループ ポリシーの ASR 除外では引用符はサポートされていません (エンジンは長いパス、スペースなどをネイティブに処理しますので、引用符を使用する必要はありません)
- ASR ルールは NT AUTHORITY\SYSTEM アカウントで実行されます。そのため、環境変数はコンピューター変数に制限されます。

## <a name="how-do-i-know-what-i-need-to-exclude"></a>除外する必要がある情報を知る方法
ASR ルールが異なると、保護フローが異なります。 構成する ASR ルールが保護する機能と、実際の実行フローがどのようにパンアウトされるのかを常に考えておきます。

例: Windows ローカル セキュリティ機関サブシステム **から** 直接読み取るローカル セキュリティ機関サブシステム (LSASS) プロセスからの資格情報の盗用をブロックすると、企業の資格情報が公開される可能性があります。

このルールにより、信頼されていないプロセスは LSASS メモリに直接アクセスできます。 プロセスが OpenProcess() 関数を使用して LSASS にアクセスしようとするたびに、PROCESS_VM_READ のアクセス権を持つルールは、そのアクセス権を特にブロックします。

:::image type="content" source="images/asrfaq1.png" alt-text="LSASS を盗む資格情報をブロックする":::

上記の例を見て、アクセス権がブロックされたプロセスの例外を実際に作成する必要がある場合、フル パスと共にファイル名を追加すると、ファイル名はブロックから除外され、LSASS プロセス メモリへのアクセスが許可された後は除外されます。 値 0 は、ASR ルールがこのファイル/プロセスを無視し、ブロック/監査を行うのを意味します。

:::image type="content" source="images/asrfaq2.png" alt-text="ファイル asr を除外する":::

## <a name="what-are-the-rules-microsoft-recommends-enabling"></a>Microsoft が有効に推奨するルールは何ですか?

可能な限りすべてのルールを有効にすることをお勧めします。 ただし、ルールを有効にしない場合があります。 たとえば、エンドポイントを管理するために Microsoft Endpoint Configuration Manager (または System Center Configuration Manager - SCCM) を使用している場合は、PSExec コマンドおよび WMI コマンドルールから発生するプロセス作成をブロックすることを有効にすることをお勧めしません。

ルール固有の各情報や警告については、パブリック ドキュメントで確認することを強 [くお勧めします](/microsoft-365/security/defender-endpoint/attack-surface-reduction.md)。
保護の複数の柱にまたがって、Office、資格情報、スクリプト、電子メールなど。WMI イベント サブスクリプションによる永続化のブロックを除くすべての ASR ルールは、1709 以降Windowsサポートされます。

* [メール クライアントと Web メールから実行可能なコンテンツをブロックする](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [すべてのアプリケーションOffice子プロセスの作成をブロックする](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [実行可能Office作成するアプリケーションのブロック](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [アプリケーションOffice他のプロセスへのコードの挿入をブロックする](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [難読化される可能性のあるスクリプトの実行をブロックする](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [Win32 API 呼び出しをブロックOfficeマクロ](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [ランサムウェアに対する高度な保護の使用](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロック](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem)する (lsass.exe)
* [PSExec および WMI コマンドから発生するプロセス作成をブロックする](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [通信Office子プロセスの作成をブロックする](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [Adobe Reader の子プロセスの作成をブロックする](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [WMI イベント サブスクリプションによる永続化のブロック](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>ASR の使用を開始する場合の推奨事項を教えてください。

監査モードで短時間 ASR ルールを実行して、ASR ルールが組織に与える影響をテストしてから有効にします。 監査モードでルールを実行している間に、誤ってブロックされる可能性のある任意の業務アプリケーションを特定し、ASR から除外できます。

大規模な組織では、ますます広範なデバイスのサブセットでルールを監査および有効にすることで、ASR ルールを "リング" で展開する方法を検討する必要があります。 Intune またはグループ ポリシー管理ツールを使用して、組織のデバイスをリングに配置できます。

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>監査モードで ASR ルールをテストしてから有効にする期間を指定します。

ルールを監査モードで約 30 日間保持し、組織全体でルールが運用される場合の動作に関する良好なベースラインを取得します。 監査期間中は、ルールによってブロックされる可能性のある任意の業務用アプリケーションを特定し、除外するルールを構成できます。

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>サードパーティのセキュリティ ソリューションから Defender for Endpoint への切り替えを行っています。 別のセキュリティ ソリューションから ASR にルールをエクスポートする "簡単な" 方法はありますか?

ほとんどの場合、別のセキュリティ ソリューションからルールをインポートするよりも [、Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) が提案するベースライン推奨事項から始める方が簡単で優れた方法です。 次に、監査モード、監視、分析などのツールを使用して、独自のニーズに合わせて新しいソリューションを構成します。 

ほとんどの ASR ルールの既定の構成は、Defender for Endpoint のリアルタイム保護と組み合わせて、多数の悪用や脆弱性から保護されます。

Defender for Endpoint 内から、カスタム インジケーターを使用して防御を更新し、特定のソフトウェア動作を許可およびブロックできます。 ASR では、ファイルとフォルダーの除外の形式でルールをカスタマイズすることもできます。 一般的なルールとして、一期間ルールを監査し、ブロックされる可能性がある任意の業務アプリケーションの除外を構成するのが最善です。

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>ASR は、パスにシステム変数とワイルドカードを含むファイルまたはフォルダーの除外をサポートしていますか?

はい。 除外されたファイル パスでのシステム変数とワイルドカードの使用の詳細については[、「ASR](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules)ルールからファイルまたは[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)フォルダーを除外する」および「ファイル拡張子とフォルダーの場所に基づいて除外を構成および検証する」を参照してください。

## <a name="do-asr-rules-cover-all-applications-by-default"></a>ASR ルールは既定ですべてのアプリケーションをカバーしますか?

ルールによって異なります。 ほとんどの ASR ルールは、Word、Microsoft Office、Excel、PowerPoint、OneNote、またはサービスなどのOutlook。 難読化される可能性のあるスクリプトの実行をブロックするなどの特定の ASR ルールは、スコープ内で一般的です。

## <a name="does-asr-support-third-party-security-solutions"></a>ASR はサードパーティのセキュリティ ソリューションをサポートしていますか?

ASR は、Microsoft Defender ウイルス対策をブロックするために使用します。 現時点では、ブロックに別のセキュリティ ソリューションを使用する ASR を構成することはできません。

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>E5 ライセンスを持ち、Defender for Endpoint と組み合わせていくつかの ASR ルールを有効にしました。 エンドポイントのイベント タイムラインの Defender に ASR イベントが一向に表示されない可能性はありますか?

ASR ルールによって通知がローカルでトリガーされるたびに、イベントに関するレポートも Defender for Endpoint ポータルに送信されます。 イベントを見つけるのに問題がある場合は、検索ボックスを使用してイベントのタイムラインをフィルター処理できます。 [セキュリティ センター] タスク バーの[構成管理] アイコンから、[攻撃表面の管理に移動] にアクセスして ASR イベントを表示することもできます。 攻撃表面の管理ページには、Defender for Endpoint に報告された ASR ルール イベントの完全な一覧を含む、レポート検出用のタブが含まれています。

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>GPO を使用してルールを適用しました。 Microsoft Outlook でルールのインデックス オプションを確認すると、"アクセスが拒否されました" というメッセージが表示されます。

インデックス作成オプションを直接開く方法は、Windows 10。

1. タスク バー **の [** 検索] アイコンWindowsします。

1. 検索 **ボックスに「インデックス オプション** 」と入力します。

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>「有病率、年齢、または信頼できるリスト条件を満たしていない限り、実行可能ファイルの実行をブロックする」というルールで使用される条件は、管理者が構成できますか?

いいえ。 このルールで使用される条件は、Microsoft クラウド保護によって管理され、信頼できるリストを常に最新の状態に保ち、世界中のデータを収集します。 ローカル管理者は、このデータを変更する書き込みアクセス権を持つ必要があります。 このルールを企業に合わせて調整するために構成する場合は、除外リストに特定のアプリケーションを追加して、ルールがトリガーされるのを防ぐことが可能です。

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>有病率、年齢、または信頼できるリスト条件を満たしない限り、ASR ルール、実行ファイルの実行 *をブロックしました*。 しばらくすると、ソフトウェアの一部が更新され、以前はブロックされなくても、ルールがブロックされます。 何か問題が起こったことはありますか?

このルールは、信頼できるアプリの一覧に有病率、年齢、または包含によって測定される既知の評判を持つ各アプリケーションに依存します。 アプリケーションをブロックまたは許可するルールの決定は、最終的には Microsoft クラウド保護によるこれらの条件の評価によって決まります。

通常、クラウド保護は、アプリケーションの新しいバージョンが以前のバージョンと十分に似ていると判断し、長さに再評価する必要はないと判断できます。 ただし、バージョンの切り替え後、特にメジャー更新後にアプリが評価を構築するには、しばらく時間がかかる場合があります。 その間に、アプリケーションを除外リストに追加して、このルールが重要なアプリケーションをブロックするのを防ぐことが可能です。 新しいバージョンのアプリケーションを頻繁に更新して操作する場合は、監査モードでこのルールを実行することを選択できます。

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>最近、ASR ルールを有効にしました。Windows ローカル セキュリティ機関サブシステム *(lsass.exe)* からの資格情報の盗用をブロックし、多数の通知を受け取っています。 どうなっているのですか。

このルールによって生成された通知は、必ずしも悪意のあるアクティビティを示すとは限りません。ただし、このルールは、マルウェアがアカウントへの不正なアクセスを取得lsass.exeをターゲットにしている場合が多いため、悪意のあるアクティビティをブロックする場合に役立ちます。 このlsass.exeは、ユーザーがログインした後、ユーザー資格情報をメモリに格納します。 Windows資格情報を使用してユーザーを検証し、ローカル セキュリティ ポリシーを適用します。

一般的な 1 日を通じて多くの正当なプロセスが資格情報を要求lsass.exe呼び出すので、このルールは特にノイズが多い場合があります。 既知の正当なアプリケーションによってこのルールが過剰な数の通知を生成する場合は、除外リストに追加できます。 他のほとんどの ASR ルールでは、lsass.exe を呼び出すのは多くのアプリケーションの通常の機能の一般的な動作のため、このルールと比較して、比較的少ない数の通知が生成されます。

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>LSA 保護と共に、Windows ローカル セキュリティ機関サブシステム *(lsass.exe)* からの資格情報の盗用をブロックするルールを有効にしてください。

このルールを有効にすると [、LSA](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) 保護も有効になっている場合、追加の保護は提供されません。 ルールと LSA 保護の両方が同じ方法で動作し、両方を同時に実行すると冗長になります。 ただし、LSA 保護を有効にできない場合があります。 このような場合は、このルールを有効にして、マルウェアを対象とするマルウェアに対して同等の保護lsass.exe。

## <a name="see-also"></a>関連項目

* [攻撃表面の縮小の概要](attack-surface-reduction.md)
* [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
* [攻撃面の減少ルールをカスタマイズする](customize-attack-surface-reduction.md)
* [攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)
* [Microsoft Defender と他のウイルス対策/マルウェア対策との互換性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)


