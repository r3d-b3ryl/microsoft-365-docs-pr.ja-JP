---
title: ランサムウェア攻撃から回復する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365管理者は、ランサムウェア攻撃から回復する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 608fac50fc65f20a612b80ed151252eb2a0c2e01
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415555"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>ユーザーのランサムウェア攻撃から回復Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

組織を保護するためにあらゆる予防措置を講じた場合でも、ランサムウェア攻撃の被害に陥 [る可能性](/windows/security/threat-protection/intelligence/ransomware-malware) があります。 ランサムウェアは大きなビジネスであり、攻撃は非常に高度です。

この記事の手順では、データを回復し、感染の内部拡散を停止する最良の機会を提供します。 開始する前に、次の項目を考慮する必要があります。

- 身代金の支払いによってファイルへのアクセスが返されるという保証はありません。 実際、身代金を支払って、より多くのランサムウェアのターゲットとなる可能性があります。

  支払い済みで、攻撃者のソリューションを使用せずに回復した場合は、銀行に問い合わせ、トランザクションをブロックできるのか確認してください。

  また、この記事で後述するように、ランサムウェア攻撃を法執行機関、詐欺報告 Web サイト、および Microsoft に報告することをお勧めします。

- 攻撃とその結果に迅速に対応することが重要です。 待つ時間が長くなると、影響を受けるデータを回復できる可能性は低くなります。

## <a name="step-1-verify-your-backups"></a>手順 1: バックアップを確認する

オフライン バックアップがある場合は、環境からランサムウェア ペイロード (マルウェア) を削除した後で、暗号化されたデータを復元できる可能性があります。

バックアップが作成されていない場合、またはバックアップがランサムウェアの影響を受けた場合は、この手順を省略できます。

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>手順 2: サーバーとExchange ActiveSyncを無効OneDrive 同期

ここで重要なポイントは、ランサムウェアによるデータ暗号化の拡散を停止することです。

ランサムウェア暗号化のターゲットとしてメールが疑われる場合は、メールボックスへのユーザー アクセスを一時的に無効にします。 Exchange ActiveSyncデバイスとメールボックス間でデータExchange Online同期します。

メールボックスのExchange ActiveSyncを無効にするには、「ユーザーのメールボックスを無効にするExchange ActiveSync[する方法」をExchange Online。](https://support.microsoft.com/help/2795303)

メールボックスへの他の種類のアクセスを無効にするには、以下を参照してください。

- [メールボックスの MAPI を有効または無効にします](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。

- [ユーザーの POP3 または IMAP4 アクセスを有効または無効にする](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

一時停止OneDrive 同期は、感染する可能性のあるデバイスによってクラウド データが更新されるのを保護するのに役立ちます。 詳細については、「How to Pause and Resume sync in [OneDrive」 を参照してください](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>手順 3: 影響を受けるデバイスからマルウェアを削除する

疑わしいすべてのコンピューターとデバイスで現在の完全なウイルス対策スキャンを実行して、ランサムウェアに関連付けられているペイロードを検出して削除します。

データを同期しているデバイス、またはマップされたネットワーク ドライブのターゲットをスキャンすることを忘れないでください。

古いクライアント[Windows Defender](https://www.microsoft.com/windows/comprehensive-security)または (古い[クライアントの場合](https://www.microsoft.com/download/details.aspx?id=5201)) を使用Microsoft Security Essentials。

ランサムウェアやマルウェアの削除にも役立つ代替手段は、 [悪意のあるソフトウェア削除ツール (MSRT) です](https://www.microsoft.com/download/details.aspx?id=9905)。

これらのオプションが機能しない場合は、[オフライン][](https://support.microsoft.com/help/17466)または [Windows Defenderマルウェアの検出と削除に関する問題のトラブルシューティング] を[試してみてください](https://support.microsoft.com/help/4466982)。

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>手順 4: クリーンアップされたコンピューターまたはデバイス上のファイルを回復する

環境からランサムウェア ペイロードを削除する前の手順を完了したら (ランサムウェアがファイルを暗号化または削除することを防ぐ)、Windows 7 の[](https://support.microsoft.com/help/17128)Windows 10 および Windows 8.1 または System Protection のファイル履歴を使用して、ローカル ファイルとフォルダーの回復を試みることもできます。

**注意**:

- また、一部のランサムウェアはバックアップ バージョンを暗号化または削除します。そのため、ファイルの履歴やシステム保護を使用してファイルを復元することはできません。 その場合は、次のセクションで説明するように、ランサムウェアやマルウェアの影響を受けOneDriveデバイスでバックアップを使用する必要があります。

- フォルダーが OneDrive に同期され、最新バージョンの Windows を使用していない場合は、ファイル履歴を使用していくつかの制限が発生する可能性があります。

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>手順 5: ファイルを復元する方法OneDrive for Business

[ファイルの復元] OneDrive for Businessを使用すると、過去 30 日以内OneDrive以前の時点に復元できます。 詳細については、「[OneDrive を復元する](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)」を参照してください。

## <a name="step-6-recover-deleted-email"></a>手順 6: 削除されたメールを復元する

まれに、ランサムウェアがすべてのメールを削除した場合、削除されたアイテムを復元できる可能性があります。 詳細については、以下を参照してください。

- [ユーザーのメールボックス内の削除済みメッセージを復元する](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Windows 版 Outlook で削除済みのアイテムを復元する](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>手順 7: 再び有効にし、Exchange ActiveSyncをOneDrive 同期

コンピューターとデバイスをクリーンアップしてデータを回復した後、手順 2 で以前に無効にした Exchange ActiveSync と OneDrive 同期 を再[び有効にすることができます](#step-2-disable-exchange-activesync-and-onedrive-sync)。

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>手順 8 (オプション): 特定のOneDrive 同期ファイルのブロック

回復後、このランサムウェアの影響を受けたOneDrive for Businessクライアントが同期されないようにすることができます。 詳細については [、「Set-SPOTenantSyncClientRestriction」を参照してください。](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>攻撃を報告する

### <a name="contact-law-enforcement"></a>法執行機関に問い合わせ

現地または連邦の法執行機関に問い合わせるべきです。 たとえば、米国にいる場合は [、FBI](https://www.fbi.gov/contact-us/field)ローカル フィールド オフィス [、IC3、](http://www.ic3.gov/complaint/default.aspx) シークレット サービスに [問い合わせできます](http://www.secretservice.gov/)。

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>国の詐欺報告 Web サイトにレポートを送信する

詐欺報告 Web サイトは、詐欺を防止し回避する方法に関する情報を提供します。 また、詐欺の被害に見合った場合に報告するメカニズムも提供されます。

- オーストラリア: [SCAMwatch](http://www.scamwatch.gov.au/)

- カナダ: [カナダ詐欺対策センター](http://www.antifraudcentre-centreantifraude.ca/)

- フランス: [アジェンス・ナショナル・デ・ラ・セクリテ・デ・システムズの情報](http://www.ssi.gouv.fr/)

- ドイツ: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- アイルランド: [ガルダ Síochána](http://www.garda.ie/)

- ニュージーランド: [消費者問題詐欺](http://www.consumeraffairs.govt.nz/scams)

- スイス [ナナレス Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)

- 英国: [アクション詐欺](http://www.actionfraud.police.uk/)

- 米国: [On Guard Online](http://www.onguardonline.gov/)

国が一覧に表示されていない場合は、地域または連邦の法執行機関に問い合います。

### <a name="submit-email-messages-to-microsoft"></a>Microsoft に電子メール メッセージを送信する

ランサムウェアを含むフィッシング メッセージを報告するには、いくつかの方法のいずれかを使用します。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="additional-ransomware-resources"></a>その他のランサムウェア リソース

主要な業界情報:

- [人が操作するランサムウェアの概要](/security/compass/human-operated-ransomware)

- [ランサムウェアや強要から迅速に保護する](/security/compass/protect-against-ransomware)

- [最新のMicrosoft セキュリティ インテリジェンスレポート](https://www.microsoft.com/securityinsights/)(P. 22-24)

- **ランサムウェア: Microsoft 365 Defender** ポータルの Threat **analytics** ノードにある、継続的な脅威レポート (以下のライセンス要件を [参照](/microsoft-365/security/defender/prerequisites#licensing-requirements))

Microsoft 365保護:

- [マルウェアと ランサムウェアからの保護](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [ランサムウェアの検出と、ファイルの復元OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)
- [ファイル内のマクロを有効またはOfficeする](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)
- [EOP と Microsoft Defender のセキュリティに関するOffice 365設定](recommended-settings-for-eop-and-office365.md)

Microsoft Security チームのブログ投稿:

- [サイバーセキュリティリスクを理解することで回復力を高める:パート 4:現在の脅威をナビゲートする (2021 年 5 月)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  「ランサムウェア **」セクションを参照** してください。

- [人が操作するランサムウェア攻撃: 予防可能な災害 (2020 年 3 月)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)
- [ランサムウェアの応答 - 支払いを行う場合と支払わない場合(2019 年 12 月)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro が透明性を持つランサムウェア攻撃に対応 (2019 年 12 月)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
- [価値あるアップグレード: 2017 年Windows 10に対する回復力を証明する次世代セキュリティ (2018 年 1 月)](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

