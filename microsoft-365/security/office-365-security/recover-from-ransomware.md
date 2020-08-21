---
title: ランサムウェア攻撃から回復する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Microsoft 365 管理者はランスムウェア攻撃から回復する方法を学習できます。
ms.openlocfilehash: 2f8e5f5deb18cadfaea7acc1cffe73abbc43010b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827835"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Microsoft 365 でランスムウェア攻撃から回復する

組織を保護するためにあらかじめすべての予防を受けたとしても、ランサムウェア攻撃の [きめはきまっても問題](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) はありません。 ランスパムウェアは大きなビジネスで、攻撃はさらに機会的であると確認されています。

このトピックの手順を実行すると、ランムウェアによって暗号化されたデータを回復するおかつ最善の方法と、組織に感染の感染の範囲を停止することができます。 開始する前に、次の項目を考慮する必要があります。

- ランサムを支払ってもファイルへのアクセスが返されるわけでは、そのことを確認するものはありません。 一般に、代金を支払うなら、よりランムウェアのターゲットを指定できます。 既に済みの場合は、攻撃者の解決策を使用することなくファイルを正常に回復すでに済ませた場合、銀行を呼び出して取引が取引をブロックできるかどうかを確認する必要があります。 また、このトピックで後述するように、ランダムウェア攻撃を法執行機関、スカム レポート Web サイト、Microsoft に報告していくことをお勧めします。

- 攻撃とその問題に対して迅速に対応するのが非常に重要です。 待つ時間が長い時間は長いので、影響を受けるデータを回復できます。

## <a name="step-1-verify-your-backups"></a>手順 1: バックアップの確認

バックアップをオフラインにしている場合は、おそらくランスタント**after**ペイロード (マルウェア) を環境から削除した後で、暗号化されたデータを復元できます。

バックアップがない場合、またはバックアップがランムウェアにも影響を受け出した場合は、この手順を省略できます。

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>手順 2: ActiveSync と OneDrive の同期を無効にする

ここで重要なのは、ランダムウェアによるデータ暗号化の詳細を停止する主要なポイントです。

電子メールが対象であると不確かな場合には、メールボックスへのユーザー アクセスを一時的に無効にする必要があります。 Exchange ActiveSyncはモバイル デバイスによって、デバイスと Exchange Online メールボックス間でデータを同期するために使用されます。

メールボックスの ActiveSync を無効にするには [、「Exchange Online でユーザーの Exchange ActiveSync を無効にする方法」を参照してください](https://support.microsoft.com/help/2795303)。

メールボックスへの他の種類のアクセスを無効にするには、次を参照してください。

- [メールボックスの MAPI を有効または無効にします](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。

- [ユーザーの POP3 または IMAP4 アクセスを有効または無効にする](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

OneDrive 同期を一時停止すると、潜在的に感染しているデバイスによるクラウド データの更新を行いないようにします。 詳細については [、OneDrive で同期を一時停止および再開する方法を参照してください](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>手順 3: 影響を受けるデバイスからマルウェアを削除する

検出されたすべてのコンピューターやデバイスで最新の更新プログラムを使ってフル ウイルス対策スキャンを実行し、ランサムウェアに関連付けられているペイロードを検出および削除します。 データの同期中のデバイスやマップされたネットワーク ドライブのターゲット (これらのコンピューターやデバイスもスキャンする必要があるコンピューターやデバイスも使用する必要がある) を使いません。

以前のクライアント [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) 使用することもできます。(以前のクライアントの場合) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)。

悪意のあるソフトウェアの削除ツール [(MSRT)](https://www.microsoft.com/download/details.aspx?id=9905)も同様の方法です。

これらのオプションが機能しない場合は、オフラインでの [Windows Defender、マルウェアの検出](https://support.microsoft.com/help/17466) と削除 [に関する問題を解決してください](https://support.microsoft.com/help/4466982)。

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>手順 4: クリーンなコンピューターまたはデバイス上でファイルを回復する

前の手順を完了してランダムウェア ペイロードを環境から削除すると (ランムウェアによるファイルの暗号化や削除を実行できません)、Windows 10 および Windows [File History](https://support.microsoft.com/help/17128) 7 の Windows 8.1 またはシステム保護を使用して、ローカル ファイルとフォルダーの回復を試行できます。

**注**:

- 一部のランムウェアはバックアップ バージョンを暗号化または削除するので、ファイル履歴またはシステム保護を使用してファイルを復元することはできません。 その場合は、次のセクションで説明されているのように、外部ドライブや、ランムウェアや OneDrive の影響を受けずに影響を受けたデバイスでバックアップを使用する必要があります。

- フォルダーが OneDrive と同期される際に、その Windows の最新バージョンを使っていない場合は、[ファイル履歴] を使用するいくつかの制限があります。

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>手順 5: OneDrive for Business でファイルを復元する

OneDrive for Business でのファイルの復元を使用すると、過去 30 日以内の以前の時刻に OneDrive 全体を復元することができます。 詳細については [、「OneDrive を復元する」を参照してください](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)。

## <a name="step-6-recover-deleted-email"></a>手順 6:削除されたメールを復元する

ランムウェアがすべてのメールを削除するというごく一般的なケースでは、削除済みアイテムを復元することができます。 詳しくは、以下を参照してください。

- [ユーザーのメールボックス内の削除済みメッセージを復元する](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Windows 版 Outlook で削除済みのアイテムを復元する](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>手順 7: クライアントと OneDrive Exchange ActiveSync再有効化する

コンピューターとデバイスをクリーンアップし、データを回復した後、手順 2 で無効にした ActiveSync と OneDrive 同期を再 [有効にすることができます](#step-2-disable-activesync-and-onedrive-sync)。

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>手順 8 (省略可能):特定のファイル拡張子に対して OneDrive の同期をブロックする

回復した後、OneDrive for Business クライアントがこのランスムウェアの影響を受けるファイルの種類を同期できなようになります。 詳細については [、「Set-SPOTenantSyncClientRestriction」を参照してください。](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>攻撃を報告する

### <a name="contact-law-enforcement"></a>連絡先の法的執行

地名または連携的な法執行年に問い合わせる必要があります。 たとえば、米国にいっている場合は [、FBI](https://www.fbi.gov/contact-us/field)のローカル フィールド オフィス [、IC3](http://www.ic3.gov/complaint/default.aspx) または Secret Service に問い合 [わせてください](http://www.secretservice.gov/)。

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>国の Scam レポート Web サイトにレポートを提出する

Scam のレポート Web サイトでは、不カムの防止方法と回避方法に関する情報が提供されます。 また、scam からレポートを送信するメカニズムも提供します。

- ストーストラリア: [SCAMwatch](http://www.scamwatch.gov.au/)

- カナダ: [カナダのオブレーダのオブレーダル](http://www.antifraudcentre-centreantifraude.ca/)

- フランス: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- ドイツ: [Bundesamt fír Sicherheit インフォットワード (Itstechnik)](https://www.bsi.bund.de/DE/Home/home_node.html)

- アイルランド: [Garda Síochána](http://www.garda.ie/)

- ニュージーランド: [カスタマー アフレース スキャミム](http://www.consumeraffairs.govt.nz/scams)

- 英国: [アクション不行](http://www.actionfraud.police.uk/)

- 米国: On [Guard Online](http://www.onguardonline.gov/)

お国が一覧にない場合は、地当しているまたは法的執行年法の執行を確認します。

### <a name="submit-email-messages-to-microsoft"></a>Microsoft にメール メッセージを送信する

ランスパンシャウェアを含むフィッシング メッセージを報告するには、いくつかの方法のいずれかを使用します。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [ランスムウェア](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [ランムウェアの応答 (支払いまたは支払いを受けないか)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro は、透明性を持つランスムウェア攻撃に対応する](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [ランスムウェアの検出と OneDrive でのファイルの回復](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security Intelligence Report](https://www.microsoft.com/securityinsights/)

- [ファイルのマクロを有効または Office無効にする](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [EOP およびドメイン 365 ATP セキュリティに関Office推奨設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [ワード ワイズ アップグレード: Windows 10 の次世代のセキュリティは、2017 年のランサムウェアの発生に対する解決策が提供されます。](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [不合格: このランサムウェアのモニュラはどういうですか?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [ロックしてマルウェアを回避する](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT 2016 年 7 月: カーベル ランサムウェア](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Cerberus のような Cerber ランのランソムウェアの 3 本。](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [トールドドランサムウェアは、Da Vinci コード (The) によって影響を与えます](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
