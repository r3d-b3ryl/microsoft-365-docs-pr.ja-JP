---
title: 手順 5 - セキュリティとコンプライアンスに関する考慮事項
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Windows と Office の重要なセキュリティとコンプライアンスに関する考慮事項について説明します。
ms.openlocfilehash: 3b0e9ae38f988b8c148fe67eeeb629a9fce23037
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869466"
---
# <a name="step-5-security-and-compliance-considerations"></a>手順 5: セキュリティとコンプライアンスに関する考慮事項

モダン デスクトップ展開の一環として、新しいセキュリティ機能とコンプライアンス機能を対象とするオプションと共に、以前のバージョンの Windows と Office から移行する際の考慮事項と共通の阻害要因について再確認します。

![](media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="135" width="135" /></td>
<td><p><strong>手順 5: セキュリティとコンプライアンスに関する考慮事項</strong></p>
<p>Windows 10 と Office 365 ProPlus には、データ、デバイスおよびユーザーを保護し、素早く脅威を検出して対応するための新しい方法が用意されています。Windows 10 への移行時のディスクの暗号化、マルウェア対策のアプリとポリシーに関連する共通の問題に対処する方法についても説明します。</p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>セキュリティとコンプライアンスは、推奨される展開プロセスの輪における 5 番目の手順であり、Windows 10 および Office 365 ProPlus のセキュリティとコンプライアンスに関する考慮事項をカバーします。完全なデスクトップ展開プロセスについては、「[モダン デスクトップ展開センター](https://aka.ms/HowToShift)」を参照してください。
>

Windows 10 単独のセキュリティ関連機能の多くが、新しいプラットフォームへの移行を促しています。また、Office 365 のクラウドサービスと Azure Active Directory を使用したアイデンティティ オプションとの統合により、データ、デバイス、およびユーザーに対する新しい継続的に更新される保護が利用できるようになります。

## <a name="overcoming-potential-security-related-deployment-blockers"></a>セキュリティに関連する潜在的な展開の阻害要因の解消

Windows 10 および Office 365 ProPlus に移行する際に追加できる新しい機能を説明して、それらのエクスペリエンスをクラウドに結び付ける前に、しばしば展開の進行を中断させることがある、いくつかの傾向について説明するところから始めましょう。

### <a name="disk-encryption"></a>ディスク暗号化

初期に発生する課題として最初に挙げられるものは、ハード ディスクの暗号化です。ハード ディスクの暗号化に関する多数のソリューションは、前のバージョンの Windows から新しいバージョンの Windows に簡単にはアップグレードできません。

一部のディスク暗号化ソリューションは、そのプラットフォームの特定のバージョンに対する Windows セットアップに '/reflectdrivers' オプションを使用するとアップグレードを実行できます。ただし、その他の多くのものは、展開に先立ってディスクの暗号化を解除して、Windows 10 のインストール後に再び暗号化することを求めます。また、一部のソリューションでは、従来の BIOS を使用するマスター ブート レコード (MBR) から UEFI に必要な GUID パーティション テーブル (GPT) への移行ができません。これが重要になる理由は、Windows 10 の新しい仮想化ベースのセキュリティ機能には UEFI を使用した 64 ビット バージョンの Windows 10 が必要になるためです。これらの機能については、この後で説明します。

こうした問題を解決するための 1 つのオプションが、Windows 10 の BitLocker を使用することです。これは、Windows 10 Pro 以上のエディションに含まれています。BitLocker を使用すると、プロセスの一環として、OS アップグレードと機能更新プログラムに対する保護を一時停止できます。

[Bitlocker の基本的な展開](https://docs.microsoft.com/ja-JP/windows/security/information-protection/bitlocker/bitlocker-basic-deployment)

### <a name="antivirus-and-antimalware-application-compatibility"></a>ウイルス対策およびマルウェア対策アプリケーションの互換性

2 番目に、Windows 7 と Windows 10 の間で [99% 以上の Windows アプリケーションに互換性がある](https://www.microsoft.com/ja-JP/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)ことがわかっていますが、多くの場合、その例外になるものがウイルス対策 (AV) アプリや仮想プライベート ネットワーク (VPN) クライアントです。こうしたアプリケーションの多くが標準以外の開発プラクティスと API を実装していて、多くの場合、ドキュメント化されていない方法を使用してシステムを保護したり、ネットワーク リソースに接続したりしています。

結果として、こうしたアプリケーションは、本質的に新しいバージョンの Windows に移行するときの変化に弱くなります。通常、AV や VPN ソフトウェアが Windows 10 で動作しない場合やアップグレード後には、使用中のアプリが修正プログラムによって Windows 10 でサポートされていてテスト済みのものに置き換えられます。

### <a name="security-policies"></a>セキュリティ ポリシー

以前のバージョンの Windows と Office に使用されていた Active Directory グループ ポリシーの設定は、Windows 10 と Office 365 ProPlus に直接変換できないことがあり、新しいセキュリティ機能とコンプライアンス機能には、古いものとは異なる考慮事項があります。現行バージョンの Windows と Office に対応するセキュリティ ポリシーのベースラインを取得するために、Microsoft Security Compliance Toolkit の使用をお勧めします。さらに、Microsoft Intune の一部としてモバイル デバイス管理ポリシーを検討してみることもお勧めします。

![](media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-3.png)

## 

## <a name="new-security-and-compliance-capabilities-in-microsoft-365"></a>Microsoft 365 の新しいセキュリティ機能とコンプライアンス機能

ここまでは、現在の保護を新しいものに移行する際の考慮事項と、移行前に注意が必要になる事項についての説明でした。ここからは、EMS 以降から Windows 10、Office 365 ProPlus およびクラウド ベースのオプションに移行したときに活用できる新しい機能について説明します。

### <a name="identity-and-access-management"></a>ID およびアクセス管理

ID およびアクセス管理の説明から始めます。Azure Active Directory は、アプリ、デバイスおよびクラウド サービスの ID 制御プレーンであり、Office 365 などのクラウド サービスに接続するための最新の方法です。条件付きアクセスを使用すると、ログイン元、使用しているデバイス、異常な動作などに基づいて、さまざまな認証要件を定義できます。

デバイス レベルでは、生体認証は、パスワードを排除するという目標に向かって進んでいるときに、デバイスやアプリへのよりシンプルで安全なアクセスのための固有の ID を提供できます。Windows Hello では、デバイス ベースの多要素認証を使用できます。これは、デバイス自体、PIN、または固有の生体認証 ID (顔や指紋など) に依存し、ポリシーによって強制実施できます。

[Azure ID 管理の基礎](https://docs.microsoft.com/ja-JP/azure/active-directory/fundamentals/identity-fundamentals)

[Azure ID ソリューションについて](https://docs.microsoft.com/ja-JP/azure/active-directory/fundamentals/understand-azure-identity-solutions)

[Azure Active Directory の条件付きアクセスとは](https://docs.microsoft.com/ja-JP/azure/active-directory/conditional-access/overview)

[Windows Hello for Business](https://docs.microsoft.com/ja-JP/windows/security/identity-protection/hello-for-business/hello-identity-verification)

### <a name="virtualization-based-security"></a>仮想化ベースのセキュリティ

現在では ID 以上に、既知の脅威と未知の脅威の両方に対応する継続的な保護を使用することもできます。そのために、Windows 10 では、セキュア ブートを使用してブート整合性とコード整合性を保証するためのコア部分に仮想化ベースのセキュリティを使用します。また、ユーザーのシークレットを Windows から切り離して維持することは、Credential Guard による資格情報の盗難防止にも役立ちます。さらに、Application Guard では、隔離されたコンテナー内でブラウザーを実行することで、ブラウザー ベースの脅威を分離および緩和できます。こうしたテクノロジのすべては、Windows 10 の仮想化ベースのセキュリティを使用します。これは、Windows 7 システムでは再現できない根本的な変更です。こうしたテクノロジには、UEFI、64 ビット Windows および SLAT による仮想化拡張機能 (ハードウェア レベル) が必要になる点に注意してください。

[仮想化ベースのセキュリティの詳細](https://docs.microsoft.com/ja-JP/windows-hardware/design/device-experiences/oem-vbs)

### <a name="security-enhancements-from-cloud-services"></a>クラウド サービスからのセキュリティの強化

クラウド サービスは、Windows と Office のセキュリティが向上する、もう 1 つのオプションの保護層を提供します。これにより、新しい攻撃と攻撃の種類をただちに検出し、抵抗して対応できる新しいレベルのほぼリアルタイムの制御が可能になります。これは、対応と更新の展開時間が本質的に遅くなる従来のソフトウェア更新および AV シグネチャ ファイルと比較したときに顕著になります。

Microsoft インテリジェント セキュリティ グラフとの併用によって、新たな脅威の情報と保護策の両方に素早くアクセスできます。ここでは、いくつかの利用できるものの例を示します。まず、Office から始めます。

**[データ損失防止](https://docs.microsoft.com/ja-JP/office365/securitycompliance/data-loss-prevention-policies)** は、Office 365 ProPlus に組み込まれています。これは、クレジット カードや個人識別番号のようなリスクの高いコンテンツが検出されたときにセキュリティ ポリシーをユーザーに通知する場合に役立ちます。ポリシーによって、ユーザーに通知することも、通知後に送信や共有をブロックすることもできます。

**[Azure Information Protection](https://docs.microsoft.com/ja-JP/azure/information-protection/rms-client/client-admin-guide)** は、Office で使用できる補完的なサービスであり、ユーザーは簡単に Office ファイルを分類してラベルを付けることができます。これにより、ラベル付きファイルに対する自動アクション (暗号化や共有のロック ダウンなど) をトリガすることができます。

また、既知の悪意のある Web サイトの動的なリストと照合してユーザーを保護するために、Office アプリケーション全体にわたる**[安全なリンク](https://docs.microsoft.com/ja-JP/office365/securitycompliance/atp-safe-links)** 保護も導入されています。

さらに、Outlook および Exchange Online の**[安全な添付ファイル](https://docs.microsoft.com/ja-JP/office365/securitycompliance/atp-safe-attachments)** は、電子メールのフィルタリングの範囲を超えて添付ファイルを検査します。リスクの高い添付ファイルが識別されると、「安全な添付ファイル」は既知の悪意のある添付ファイルについてユーザーに通知し、電子メールから削除します。

**[Office 365 Message Encryption](https://docs.microsoft.com/ja-JP/office365/securitycompliance/encryption)** (OME) も、送信された電子メールと添付ファイルの保護に使用できます。これにより、意図した受信者のみが電子メールの内容を表示できるようになります。OME は、Google、Yahoo、および Microsoft のコンシューマ アカウント認証とシームレスに連動します。また、ワンタイム パスコードにより、その他の電子メール サービスのユーザーも安全に電子メールを受信できます。

#### <a name="additional-windows-10-protections"></a>その他の Windows 10 の保護機能

**[Windows Defender アプリケーション制御](https://docs.microsoft.com/ja-JP/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)** (Windows 10) は、Microsoft が安全性について確認したアプリケーションの承認済みの許可リストと拒否リストによって動作します。そのすべては、Microsoft Intune を使用するエンドポイント保護ポリシーによって管理されます。

**[Windows Defender Advanced Threat Protection](https://docs.microsoft.com/ja-JP/windows/security/threat-protection/windows-defender-atp/overview)** は、予防的な保護、侵害後の検出、自動調査、および対応のための統一されたプラットフォームです。これにより、エンドポイントがサイバー脅威から保護されます。高度な攻撃とデータ侵害を検出し、セキュリティ インシデントを自動化して、セキュリティ体制を強化します。

**[Exploit Guard](https://docs.microsoft.com/ja-JP/windows/security/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)** は、Windows へのマルウェアの侵入を阻止し、信頼されていないプロセスによる保護されたフォルダーへのアクセスを禁止することで、実行中のアプリケーションの攻撃対象になる部分を減らすために役立ちます。

#### <a name="microsoft-intune"></a>Microsoft Intune

[Microsoft Intune](https://docs.microsoft.com/ja-JP/intune/introduction-intune) は、IOS、Android および Windows デバイスを含むモバイル シナリオに対応するクラウドベースの管理サービスとして機能します。System Center Configuration Manager によって管理される特定のワークロードに対する制御を補完および拡張するための共同管理に向けた構成が可能になりました。その利点の 1 つは、保護されたリソースにアクセスするデバイスは、管理対象ではないデバイス、ドメインに参加していないデバイスまたは Azure AD に参加していないデバイスであったとしても、デバイス管理への登録を要件にできることです。また、オペレーティング システムおよびアプリケーション レベルで、詳細な構成とコンプライアンス ポリシーの強制適用を利用することもできます。アプリケーションのポリシーと設定は、Microsoft Intune を使用することで一元的に構成して Windows 10 の Office 365 ProPlus と Store アプリに強制適用できます。

## <a name="next-step"></a>次の手順

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[手順 6: OS の展開と機能更新プログラム](https://aka.ms/mdd6)

## <a name="previous-step"></a>前の手順 

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[手順 4: ユーザーのファイルと設定](https://aka.ms/mdd4)
