---
title: ランサムウェア攻撃からの回復
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Office 365 管理者は、ランサムウェア攻撃から回復する方法について説明します。
ms.openlocfilehash: 04cfd2f2417b0c2e084a88f9ee156521339b18c4
ms.sourcegitcommit: e47694dedf7e213167d3d979a44c07c668bba543
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41932375"
---
# <a name="recover-from-a-ransomware-attack-in-office-365"></a>Office 365 でランサムウェア攻撃から回復する

Office 365 組織を保護するためにすべての予防措置を講じたとしても、[ランサムウェア](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)攻撃に被害を与えることができます。 ランサムウェアは大規模なものであり、攻撃は高度なものとなっています。

このトピックの手順に従って、ランサムウェアによって暗号化されたデータを復元する機会が最善になり、Office 365 組織における感染の拡大を止めることができます。 開始する前に、次の項目を考慮する必要があります。

- Ransom からファイルへのアクセスが返される保証はありません。 実際には、ransom を支払うことで、ランサムウェアをさらに確保することができます。 既に有料になっていても、攻撃者の解決策を使用せずにファイルを正常に復元できた場合は、銀行に電話して、トランザクションをブロックできるかどうかを確認する必要があります。 また、このトピックの後半で説明するように、ランサムウェア攻撃を司法機関、詐欺報告用 web サイト、および Microsoft に報告することをお勧めします。

- 攻撃とその影響に迅速に対応することが非常に重要です。 待機時間が長くなるほど、影響を受けるデータを回復できる可能性が低くなります。

## <a name="step-1-verify-your-backups"></a>手順 1: バックアップを確認する

オフラインバックアップを使用している場合は、使用している環境からランサムウェアペイロード (マルウェア) を削除**した後**で、暗号化されたデータを復元する可能性があります。

バックアップがない場合、またはバックアップがランサムウェアの影響を受けている場合は、この手順を省略できます。

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>手順 2: ActiveSync と OneDrive の同期を無効にする

ここで重要な点は、ランサムウェアによるデータ暗号化の拡散を停止することです。

メールが対象になると考えられる場合は、メールボックスへのユーザーアクセスを一時的に無効にする必要があります。 Exchange ActiveSync は、モバイルデバイスがデバイスと Exchange Online メールボックスの間でデータを同期するために使用されます。

メールボックスの ActiveSync を無効にするには、「 [How to Disable Exchange activesync In Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365)」を参照してください。

メールボックスへの他の種類のアクセスを無効にするには、以下を参照してください。

- [メールボックスの MAPI を有効または無効](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)にします。

- [ユーザーの POP3 または IMAP4 アクセスを有効または無効にする](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

OneDrive 同期を一時停止すると、潜在的に感染しているデバイスによるクラウドデータの更新を防ぐことができます。 詳細については、「 [OneDrive で同期を一時停止および再開する方法](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)」を参照してください。

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>手順 3: 影響を受けたデバイスからマルウェアを削除する

すべての疑いのあるコンピューターおよびデバイスで最新の更新プログラムを使用して完全なウイルス対策スキャンを実行し、ランサムウェアに関連付けられているペイロードを検出して削除します。 データを同期しているデバイス、またはマップされたネットワークドライブのターゲット (それらのコンピューターとデバイスもスキャンする必要がある) を忘れないようにしてください。

[Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)は、 [Windows Defender](https://www.microsoft.com/windows/comprehensive-security)または (古いクライアントの場合) を使用できます。

また、ランサムウェアまたはマルウェアを削除するための代替手段として、悪意のある[ソフトウェアの削除ツール (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905)もあります。

これらのオプションが機能しない場合は、[マルウェアの検出と削除に関する問題のトラブルシューティング](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)を[Windows Defender オフライン](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc)で試みることができます。

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>手順 4: クリーニングされたコンピューターまたはデバイス上のファイルを復元する

前の手順を完了して、使用している環境からランサムウェアのペイロードを削除します (これにより、ランサムウェアによるファイルの暗号化や削除ができなくなります)。 windows 7 では、windows 8.1 10 の[ファイル履歴](https://support.microsoft.com/help/17128/windows-8-file-history)を使用して、ローカルのファイルとフォルダーの回復を試みることができます。

**注**:

- また、一部のランサムウェアはバックアップバージョンを暗号化または削除するので、ファイル履歴またはシステム保護を使用してファイルを復元することはできません。 その場合は、次のセクションで説明するように、ランサムウェアまたは OneDrive の影響を受けない外部ドライブまたはデバイスでバックアップを使用する必要があります。

- フォルダーが OneDrive に同期されていて、最新バージョンの Windows を使用していない場合は、ファイル履歴を使用するといくつかの制限があります。

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>手順 5: OneDrive for Business のファイルを復元する

OneDrive for Business では、保存したファイルを回復することができます。 次の 2 つの方法があります。

- [OneDrive web サイト](https://support.office.com/article/159cad6d-d76e-4981-88ef-de6e96c93893)を使用します。

- 多数のファイルが影響を受けた場合は、"サイトコレクションの復元" のサポート要求を作成できます。 この要求では、過去14日以内にファイルを復元できます。

## <a name="step-6-recover-deleted-email"></a>手順 6: 削除済みメールを復元する

ランサムウェアによってすべての電子メールが削除された場合は、削除済みアイテムを回復できる場合があります。 詳細については、以下を参照してください。

- [ユーザーのメールボックス内の削除済みメッセージを復元する](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Windows 版 Outlook で削除済みのアイテムを復元する](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>手順 7: Exchange ActiveSync と OneDrive の同期を再度有効にする

コンピューターとデバイスを消去してデータを回復したら、[手順 2](#step-2-disable-activesync-and-onedrive-sync)で以前に無効にした ActiveSync と OneDrive の同期を再度有効にすることができます。

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>手順 8 (オプション): 特定のファイル拡張子に対して OneDrive 同期をブロックする

回復した後で、OneDrive for Business クライアントがこのランサムウェアの影響を受けたファイルの種類を同期できないようにすることができます。 詳細については、「 [get-spotenantsyncclientrestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) 」を参照してください。

## <a name="report-the-attack"></a>攻撃を報告する

### <a name="contact-law-enforcement"></a>連絡先の法的執行

地域または連邦法執行機関に連絡する必要があります。 たとえば、米国内にいる場合は、 [FBI ローカルフィールド office](https://www.fbi.gov/contact-us/field)、 [IC3](http://www.ic3.gov/complaint/default.aspx) 、または[Secret サービス](http://www.secretservice.gov/)に問い合わせることができます。

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>国内の詐欺報告 web サイトにレポートを提出する

詐欺の報告 web サイトは、詐欺を防止および回避する方法についての情報を提供します。 また、詐欺の被害を受けた場合に報告するメカニズムも提供します。

- オーストラリア: [Scamwatch](http://www.scamwatch.gov.au/)

- カナダ:[カナダの詐欺防止センター](http://www.antifraudcentre-centreantifraude.ca/)

- フランス: [agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- ドイツ: [Bundesamt Für Sicherheit in Der Informationst k](https://www.bsi.bund.de/DE/Home/home_node.html)

- アイルランド: [Garda Síochána](http://www.garda.ie/)

- ニュージーランド:[消費者詐欺詐欺](http://www.consumeraffairs.govt.nz/scams)

- 英国:[アクションの不正行為](http://www.actionfraud.police.uk/)

- 米国:[ガードオンライン](http://www.onguardonline.gov/)

お住まいの国が表示されない場合は、地域または連邦法執行機関にお問い合わせください。

### <a name="submit-email-messages-to-microsoft"></a>Microsoft に電子メールメッセージを送信する

ランサムウェアを含むフィッシングメッセージを報告するには、 [「スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)」の手順に従ってください。

## <a name="see-also"></a>関連項目

- [サム](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [サムウェア対策応答—支払いを行うかどうかを確認します。](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro は、透過可能なランサム攻撃に応答します。](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [OneDrive でのファイルのランサムウェア検出と復元](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft セキュリティインテリジェンスレポート](https://www.microsoft.com/securityinsights/)

- [Office ファイルのマクロを有効または無効にする](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [EOP および Office 365 の ATP セキュリティに関する推奨設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [アップグレードに値する場合: Windows 10 の次世代セキュリティは、2017でランサムウェアに対する回復性を証明します。](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Mas なし、Samas このランサムウェアの modus の動作](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky マルウェア、幸運による回避](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT 2016 年7月: Cerber ランサムウェア](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Cer(英語) のような、Cerber ランサムウェアの3つのヘッド](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [() Da Vinci コードによって影響を受ける Troldesh ランサムウェア](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
