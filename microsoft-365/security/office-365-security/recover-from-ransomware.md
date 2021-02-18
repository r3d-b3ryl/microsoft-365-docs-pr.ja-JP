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
description: Microsoft 365 管理者は、ランサムウェア攻撃から回復する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 120dd9ae71f04d6921fae95965f56f0a08f1280c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289307"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Microsoft 365 でランサムウェア攻撃から回復する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

組織を保護するためにあらゆる予防措置を講じた場合でも、ランサムウェア攻撃の被害を [受け取る可能性](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) があります。 ランサムウェアは大企業であり、攻撃は非常に高度です。

この記事の手順では、データを回復し、感染の内部拡散を止める最善の機会を提供します。 開始する前に、次の項目を考慮する必要があります。

- 身代金を支払ってファイルへのアクセスを返す保証はありません。 実際、身代金を支払うなら、より多くのランサムウェアのターゲットになれる可能性があります。

  既に支払い済みで、攻撃者のソリューションを使用せずに回復した場合は、銀行に問い合わせ、取引をブロックすることができるか確認してください。

  また、この記事で後述するように、ランサムウェア攻撃を法執行機関、詐欺報告 Web サイト、および Microsoft に報告することをお勧めします。

- 攻撃とその結果に迅速に対応することが重要です。 待つ時間が長くなると、影響を受けるデータを回復できる可能性が低くなります。

## <a name="step-1-verify-your-backups"></a>手順 1: バックアップを確認する

オフライン バックアップがある場合は、環境からランサムウェア ペイロード (マルウェア) を削除した後、暗号化されたデータを復元できる可能性があります。

バックアップを作成しない場合、またはバックアップがランサムウェアの影響を受けた場合は、この手順を省略できます。

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>手順 2: OneDrive Exchange ActiveSync同期を無効にする

ここでの重要なポイントは、ランサムウェアによるデータ暗号化の拡散を停止することです。

ランサムウェア暗号化のターゲットとしてメールが疑われる場合は、メールボックスへのユーザー アクセスを一時的に無効にします。 Exchange ActiveSyncと Exchange Online メールボックス間でデータを同期します。

メールボックスのExchange ActiveSyncを無効にするには、Exchange Online でユーザーのメールボックスのExchange ActiveSyncを [無効にする方法を参照してください](https://support.microsoft.com/help/2795303)。

メールボックスへの他の種類のアクセスを無効にするには、以下を参照してください。

- [メールボックスの MAPI を有効または無効にします](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。

- [ユーザーの POP3 または IMAP4 アクセスを有効または無効にする](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

OneDrive 同期を一時停止すると、感染している可能性のあるデバイスによってクラウド データが更新されるのを保護できます。 詳細については [、「OneDrive で同期を一時停止および再開する方法」を参照してください](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>手順 3: 影響を受けるデバイスからマルウェアを削除する

疑わしいすべてのコンピューターとデバイスで最新の完全なウイルス対策スキャンを実行し、ランサムウェアに関連付けられているペイロードを検出して削除します。

データを同期しているデバイスや、マップされたネットワーク ドライブのターゲットをスキャンすることを忘れないでください。

以前 [のクライアントWindows Defender](https://www.microsoft.com/windows/comprehensive-security) (古い [クライアントの場合](https://www.microsoft.com/download/details.aspx?id=5201)) を使用Microsoft Security Essentials。

ランサムウェアやマルウェアの削除にも役立つ代替手段として、悪意のあるソフトウェアの削除 [ツール (MSRT) があります](https://www.microsoft.com/download/details.aspx?id=9905)。

これらのオプションが機能しない場合は、[オフライン] または [マルウェアの [Windows Defender](https://support.microsoft.com/help/17466) と削除に関する問題のトラブルシューティング] を [試してください](https://support.microsoft.com/help/4466982)。

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>手順 4: クリーンアップされたコンピューターまたはデバイス上のファイルを復元する

ランサムウェア ペイロードを環境から削除する前の手順を完了したら (ランサムウェアによるファイルの暗号化や削除を防ぐ)、Windows 10 および[](https://support.microsoft.com/help/17128)Windows 8.1 のファイル履歴、または Windows 7 の System Protection を使用して、ローカルのファイルとフォルダーの回復を試みることもできます。

**注**:

- 一部のランサムウェアはバックアップ バージョンも暗号化または削除します。そのため、ファイル履歴やシステム保護を使用してファイルを復元することはできません。 その場合は、次のセクションで説明するように、ランサムウェアや OneDrive の影響を受けない外部ドライブまたはデバイスでバックアップを使用する必要があります。

- フォルダーが OneDrive と同期され、最新バージョンの Windows を使用していない場合は、ファイル履歴の使用にいくつかの制限が発生する可能性があります。

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>手順 5: OneDrive for Business でファイルを復元する

OneDrive for Business でのファイルの復元では、過去 30 日以内に OneDrive 全体を以前の時点に復元できます。 詳細については [、「OneDrive を復元する」を参照してください](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)。

## <a name="step-6-recover-deleted-email"></a>手順 6: 削除されたメールを復元する

ランサムウェアによってすべてのメールが削除されるというまれなケースでは、おそらく削除済みアイテムを回復できます。 詳細については、以下を参照してください。

- [ユーザーのメールボックス内の削除済みメッセージを復元する](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Windows 版 Outlook で削除済みのアイテムを復元する](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>手順 7: 同期と OneDrive Exchange ActiveSyncを再び有効にする

コンピューターとデバイスをクリーンアップしてデータを回復した後、手順 2 で無効にした Exchange ActiveSync と OneDrive の同期を再 [び有効にすることができます](#step-2-disable-exchange-activesync-and-onedrive-sync)。

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>手順 8 (オプション): 特定のファイル拡張子に対する OneDrive 同期をブロックする

回復した後、OneDrive for Business クライアントがこのランサムウェアの影響を受けたファイルの種類を同期されないようにすることができます。 詳細については[、「Set-SPOTenantSyncClientRestriction」を参照してください](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)。

## <a name="report-the-attack"></a>攻撃を報告する

### <a name="contact-law-enforcement"></a>法執行機関に問い合わせ

現地または連邦法執行機関に問い合わせが必要です。 たとえば、米国にいる場合は [、FBI](https://www.fbi.gov/contact-us/field)のローカル フィールド オフィス [、IC3、](http://www.ic3.gov/complaint/default.aspx) またはシークレット サービスに [問い合わせできます](http://www.secretservice.gov/)。

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>お客様の国の詐欺報告 Web サイトにレポートを送信する

詐欺報告 Web サイトは、詐欺を防止および回避する方法に関する情報を提供します。 また、詐欺の被害を受けした場合に報告するメカニズムも提供します。

- オーストラリア: [SCAMwatch](http://www.scamwatch.gov.au/)

- カナダ: [カナダ詐欺対策センター](http://www.antifraudcentre-centreantifraude.ca/)

- フランス: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- ドイツ: [Bundesamt fの Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- アイルランド: [An Ireland Síochía](http://www.garda.ie/)

- ニュージーランド: [消費者消費者詐欺](http://www.consumeraffairs.govt.nz/scams)

- 英国: [アクション詐欺](http://www.actionfraud.police.uk/)

- 米国: [On Guard Online](http://www.onguardonline.gov/)

お客様の国が一覧に表示されていない場合は、お近くの法執行機関または連邦法執行機関にお問い合ください。

### <a name="submit-email-messages-to-microsoft"></a>Microsoft に電子メール メッセージを送信する

ランサムウェアを含むフィッシング メッセージは、いくつかの方法のいずれかを使用して報告できます。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [ランサムウェア](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [ランサムウェアの応答 — 支払いを行うのか、それとも支払わないか。](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Respond は、透明性を持つランサムウェア攻撃に対応します](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [OneDrive でのランサムウェア検出とファイルの回復](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft セキュリティ インテリジェンス レポート](https://www.microsoft.com/securityinsights/)

- [ファイル内のマクロを有効またはOfficeする](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [EOP と Microsoft Defender の 365 セキュリティOffice推奨設定](recommended-settings-for-eop-and-office365-atp.md)

- [価値あるアップグレード: Windows 10 の次世代セキュリティは、2017 年のランサムウェアの発生に対する回復力を証明します](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [いいえ、サマ: このランサムウェアの変更オペランドには何がありますか?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [ロックされたマルウェアを避けるためのマルウェア](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT 2016 年 7 月: Cerber ランサムウェア](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Cerberus に似た Cerber ランサムウェアの 3 人のヘッド](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [(the) Da The 数人のコードの影響を受ける、ストルデシ ランサムウェア](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
