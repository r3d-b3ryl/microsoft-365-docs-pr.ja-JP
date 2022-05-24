---
title: ランサムウェア攻撃から回復する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- m365solution-ransomware
description: Microsoft 365管理者は、ランサムウェア攻撃から回復する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 328457e37ea6ae351abb2c5d5f0089246145b32c
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648659"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Microsoft 365でのランサムウェア攻撃から回復する

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

組織を保護するためにあらゆる予防措置を講じても、 [ランサムウェア](/windows/security/threat-protection/intelligence/ransomware-malware) 攻撃の被害を受ける可能性があります。 ランサムウェアは大きなビジネスであり、今日の脅威環境では、高度[な攻撃のターゲット](https://i.blackhat.com/USA21/Wednesday-Handouts/us-21-Cloudy-With-A-Chance-Of-APT-Novel-Microsoft-365-Attacks-In-The-Wild.pdf)が増え続けていますMicrosoft 365。

この記事の手順では、データを回復し、感染の内部拡散を停止する最適な機会を提供します。 開始する前に、次の項目を考慮する必要があります。

- 身代金を支払うとファイルへのアクセスが返されるという保証はありません。 実際、身代金を支払うと、より多くのランサムウェアのターゲットになる可能性があります。

  既に支払い済みで、攻撃者のソリューションを使用せずに復旧した場合は、銀行に連絡して、トランザクションをブロックできるかどうかを確認してください。

  また、この記事で後述するように、ランサムウェア攻撃を法執行機関、詐欺報告 Web サイト、Microsoft に報告することをお勧めします。

- 攻撃とその結果に迅速に対応することが重要です。 待機時間が長いほど、影響を受けるデータを回復できる可能性は低くなります。

## <a name="step-1-verify-your-backups"></a>手順 1: バックアップを確認する

オフライン バックアップがある場合は、環境からランサムウェア ペイロード (マルウェア) を削除し、Microsoft 365環境に不正アクセスがないことを確認した **後** に、暗号化 **されたデータを** 復元できる可能性があります。

バックアップがない場合、またはバックアップがランサムウェアの影響を受けた場合は、この手順をスキップできます。

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>手順 2: Exchange ActiveSyncとOneDrive 同期を無効にする

ここで重要なのは、ランサムウェアによるデータ暗号化の拡散を阻止することです。

ランサムウェア暗号化のターゲットとして電子メールが疑われる場合は、メールボックスへのユーザー アクセスを一時的に無効にします。 Exchange ActiveSyncは、デバイスとExchange Onlineメールボックスの間でデータを同期します。

メールボックスのExchange ActiveSyncを無効にするには、「[Exchange OnlineのユーザーのExchange ActiveSyncを無効にする方法」を](https://support.microsoft.com/help/2795303)参照してください。

メールボックスへの他の種類のアクセスを無効にするには、次を参照してください。

- [メールボックスの MAPI を有効または無効にします](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。

- [ユーザーの POP3 または IMAP4 アクセスを有効または無効にする](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

OneDrive 同期を一時停止すると、感染する可能性のあるデバイスによってクラウド データが更新されないように保護できます。 詳細については、「[OneDriveで同期を一時停止および再開する方法](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)」を参照してください。

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>手順 3: 影響を受けるデバイスからマルウェアを削除する

疑わしいすべてのコンピューターとデバイスで最新のフル ウイルス対策スキャンを実行し、ランサムウェアに関連付けられているペイロードを検出して削除します。

データを同期しているデバイスや、マップされたネットワーク ドライブのターゲットを必ずスキャンしてください。

[Windows Defender](https://www.microsoft.com/windows/comprehensive-security)または (古いクライアントの場合) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)を使用できます。

ランサムウェアやマルウェアの削除にも役立つ代替手段として、 [悪意のあるソフトウェア削除ツール (MSRT) があります](https://www.microsoft.com/download/details.aspx?id=9905)。

これらのオプションが機能しない場合は、[オフラインWindows Defender](https://support.microsoft.com/help/17466)試すか、[マルウェアの検出と削除に関する問題のトラブルシューティングを](https://support.microsoft.com/help/4466982)試すことができます。

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>手順 4: クリーニングされたコンピューターまたはデバイス上のファイルを回復する

環境からランサムウェア ペイロードを削除する前の手順を完了すると (ランサムウェアによるファイルの暗号化または削除が防止されます)、Windows 11、Windows 10、Windows 8.1で[ファイル履歴](https://support.microsoft.com/help/17128)を使用し、Windows 7 の System Protection を使用してローカル ファイルとフォルダーの回復を試みることができます。

**注**:

- 一部のランサムウェアではバックアップ バージョンも暗号化または削除されるため、ファイル履歴または System Protection を使用してファイルを復元することはできません。 その場合は、次のセクションで説明するように、ランサムウェアやOneDriveの影響を受けなかった外部ドライブまたはデバイスでバックアップを使用する必要があります。

- フォルダーがOneDriveに同期されていて、最新バージョンのWindowsを使用していない場合は、ファイル履歴の使用にいくつかの制限がある可能性があります。

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>手順 5: OneDrive for Business内のファイルを回復する

OneDrive for Businessファイルの復元では、過去 30 日以内にOneDrive全体を以前の時点に復元できます。 詳細については、「[OneDrive を復元する](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)」を参照してください。

## <a name="step-6-recover-deleted-email"></a>手順 6: 削除されたメールを回復する

ランサムウェアによってすべてのメールが削除されたというまれなケースでは、削除されたアイテムを回復できる可能性があります。 詳細については、以下を参照してください。

- [ユーザーのメールボックス内の削除済みメッセージを復元する](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Windows 版 Outlook で削除済みのアイテムを復元する](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>手順 7: Exchange ActiveSyncとOneDrive 同期を再度有効にする

コンピューターとデバイスをクリーニングしてデータを回復したら、[手順 2](#step-2-disable-exchange-activesync-and-onedrive-sync) で以前に無効にしたExchange ActiveSyncとOneDrive 同期を再度有効にすることができます。

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>手順 8 (省略可能): 特定のファイル拡張子のOneDrive 同期をブロックする

回復した後、OneDrive for Business クライアントがこのランサムウェアの影響を受けたファイルの種類を同期できないようにすることができます。 詳細については、「[Set-SPOTenantSyncClientRestriction」を](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)参照してください。

## <a name="report-the-attack"></a>攻撃を報告する

### <a name="contact-law-enforcement"></a>法執行機関に問い合わせる

ローカルまたは連邦の法執行機関に問い合わせる必要があります。 たとえば、米国にいる場合は、[FBI ローカル フィールド オフィス](https://www.fbi.gov/contact-us/field)、[IC3](http://www.ic3.gov/complaint/default.aspx)、または[シークレット サービス](http://www.secretservice.gov/)に問い合わせてください。

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>国の詐欺報告 Web サイトにレポートを送信する

詐欺レポート Web サイトでは、詐欺を防止および回避する方法に関する情報が提供されます。 また、詐欺の被害に遭った場合に報告するメカニズムも提供されます。

- オーストラリア: [SCAMwatch](http://www.scamwatch.gov.au/)

- カナダ: [カナダ詐欺対策センター](http://www.antifraudcentre-centreantifraude.ca/)

- フランス: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- ドイツ: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- アイルランド: [1 つのガルーダ Síochána](http://www.garda.ie/)

- ニュージーランド: [コンシューマー アフェアス 詐欺](http://www.consumeraffairs.govt.nz/scams)

- スイス [ナショナルズ Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)

- 英国: [アクション詐欺](http://www.actionfraud.police.uk/)

- 米国: [On Guard Online](http://www.onguardonline.gov/)

お使いの国が一覧にない場合は、現地または連邦の法執行機関に問い合わせてください。

### <a name="submit-email-messages-to-microsoft"></a>Microsoft に電子メール メッセージを送信する

ランサムウェアを含むフィッシング メッセージは、いくつかの方法のいずれかを使用して報告できます。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="additional-ransomware-resources"></a>その他のランサムウェア リソース

Microsoft の主な情報:

- [ランサムウェアの脅威の増大](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/)、2021 年 7月 20 日付け Microsoft On the Issues のブログ投稿
- [人が操作するランサムウェア](/security/compass/human-operated-ransomware)
- [ランサムウェアや強要から迅速に保護する](/security/compass/protect-against-ransomware)
- [2021 Microsoft Digital Defense Report](https://www.microsoft.com/security/business/microsoft-digital-defense-report) (10- 19 ページを参照ください)
- [ランサムウェア: Microsoft 365 Defender ポータルの脅威分析ノードの蔓延する継続的な脅威](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview)に関するレポート (これらの「ライセンス要件」 を参照ください)

Microsoft 365:

- [Microsoft 365 テナントにランサムウェア保護を展開する](/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [Azure と Microsoft 365 を使用してランサムウェアの回復性を最大化する](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [マルウェアと ランサムウェアからの保護](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [ランサムウェアからWindows PC を保護する](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [SharePoint Online でのランサムウェアの処理](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- [Microsoft 365 Defender](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag)ポータルでのランサムウェアの脅威分析レポート

Microsoft 365 Defender:

- [高度な検索でランサムウェアを検索する](/microsoft-365/security/defender/advanced-hunting-find-ransomware)

Microsoft Azure

- [ランサムウェア攻撃に対する Azure 防御](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Azure と Microsoft 365 を使用してランサムウェアの回復性を最大化する](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [ランサムウェアから保護するためのバックアップと復元の計画](/security/compass/backup-plan-to-protect-against-ransomware)
- [Microsoft Azure Backup を使用したランサムウェアからの保護に役立つ](https://www.youtube.com/watch?v=VhLOr2_1MCg) (26 分間のビデオ)
- [体系的な ID 侵害からの回復](/azure/security/fundamentals/recover-from-identity-compromise)
- [Microsoft Sentinel での高度な多段階攻撃検出](/azure/sentinel/fusion#ransomware)
- [Microsoft Sentinel でのランサムウェアのフュージョン検出](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Defender for Cloud Apps

-  [Defender for Cloud Apps で異常検出ポリシーを作成する](/cloud-app-security/anomaly-detection-policy)

Microsoft Security チームのブログ投稿:

- [ランサムウェアを防止して回復するための 3 つの手順 (2021 年 9 月)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [人が操作するランサムウェアの対策ガイド: パート 1 (2021 年 9 月)](https://www.microsoft.com/security/blog/2021/09/20/a-guide-to-combatting-human-operated-ransomware-part-1/)

  Microsoft の検出対応チーム (DART) がランサムウェア インシデント調査を実施する方法に関する重要な手順。

- [人が操作するランサムウェアの対策ガイド: パート 2 (2021 年 9 月)](https://www.microsoft.com/security/blog/2021/09/27/a-guide-to-combatting-human-operated-ransomware-part-2/)

  推奨事項とベスト プラクティス。

- [サイバーセキュリティ リスクを理解することで回復力を高める パート 4—現在の脅威をナビゲートする(2021 年 5 月)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  「**ランサムウェア**」セクションを参照 してください。

- [人が操作するランサムウェア攻撃: 予防可能な災害 (2020 年 3 月)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  実際の攻撃の攻撃チェーン分析が含まれます。

- [ランサムウェアの応答 - 支払うべきか、支払わざるべきか? (2019 年 12 月)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro のランサムウェア攻撃に対する透明性のある対応 (2019 年 12 月)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
