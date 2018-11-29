---
title: デバイスの構成
description: Microsoft 管理デスクトップ デバイスに適用される既定のポリシーについて説明します。
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 5a97f44641ac38a8785bde66819dbfffffee946d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869446"
---
# <a name="device-configuration"></a>デバイスの構成


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

新しい Microsoft 管理デスクトップ デバイスに準備されているが、右の構成では、Microsoft 管理されたデスクトップ用に最適化されていることを確認します。これには、登録プロセスの一部として構成されている既定のポリシーのセットが含まれます。競合を避けるためには、これらのポリシーを変更しないようにします。 

デバイスは、署名の画像を受信し、最初のユーザーがログインすると、Azure Active Directory ドメインに参加します。デバイスが自動的にインストール必要なポリシーとアプリケーションに必要な IT の介入なし。

## <a name="why-mdm-over-group-policy"></a>なぜ MDM をグループ ポリシー経由で

グループ ポリシーの代わりに、モバイル デバイス管理 (MDM) を使用するいくつかの理由があります。

- セキュリティの MDM のポリシーは、現代の世界でより安全です。グループ ポリシーでは、設置型の id を使用して最適に動作するよう設計されています。MDM は、クラウド id 管理 (Azure Active Directory (AD の Azure)) で最適に動作するよう設計されています。
- 信頼性の MDM のポリシーより信頼性の高いポリシーの展開を提供します。MDM の設定は、グループ ポリシー オブジェクト (GPO) のポリシーを上書きします。Windows 10、1803 のバージョンで始まる MDM の設定が優先順位をグループ ポリシーの値です。これは、現代の管理に移行するお客様をサポートします。 
- ポリシーの展開の詳細に監視・管理されたデスクトップの Microsoft のビジョンと位置を合わせます。停止/再開の展開が必要な場合に機能を備えたリング ベースのアプローチを段階的にロールアウト ポリシーを変更するをサポートします。

## <a name="default-policies"></a>既定のポリシー

このテーブルのハイライト ポリシーを既定のデバイスの提供処理中に Microsoft の管理されたデスクトップのすべてのデバイスに適用されます。競合を避けるためには、これらのポリシーを変更しないようにします。検出されたすべての管理されたデスクトップの Microsoft によって管理されるオブジェクトに Microsoft 管理デスクトップ操作のチームは、未承認の変更を元に戻します。

ポリシー | 説明
--- | ---
セキュリティ基準 | MDM の[マイクロソフトのセキュリティの基準](https://docs.microsoft.com/windows/device-security/windows-security-baselines)は、管理されたデスクトップの Microsoft のすべてのデバイスの構成されます。この基準は、業界の標準的な構成です。公開されたら、十分にテストし、Microsoft 管理されたデスクトップのデバイスを保持するマイクロソフトのセキュリティ専門家が確認し、最新のワークプ レース内でアプリケーションをセキュリティで保護します。<br><br>常に進化するセキュリティ脅威の状況に脅威を軽減するには、マイクロソフトのセキュリティの基準による更新し、Windows 10 機能更新のたびに、Microsoft 管理デスクトップ デバイスに配備します。<br><br>詳細については、 [Windows の 10 のセキュリティ基準](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)を参照してください。
Microsoft 管理されたデスクトップは、セキュリティ テンプレートを推奨します。 | ユーザー エクスペリエンスを最適化するセキュリティ基準を推奨する変更のセット。 これらの変更は、[セキュリティの追加条項](#security-addendum)に記載されています。付属のポリシーの更新は、必要に応じてで発生します。  
デバイスのコンプライアンス | これらのポリシーは、管理されたデスクトップの Microsoft のすべてのデバイスの既定値で構成されます。セキュリティの次の条件のいずれかが満たされていない場合、非準拠デバイスが報告されます。<br>のデバイス上のデータを保護するために、BitLocker デバイスの暗号化を有効にします。詳細についてを参照してください[の概要の BitLocker デバイス暗号化 Windows 10 にします](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)。<br>-セキュリティで保護されたブートが有効になり、実行することができます前に、デバイス上のファームウェア イメージを検証するために、適用されます。詳細についてを参照してください[ブートおよびデバイスのセキュリティで保護された暗号化の概要です](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)。<br>Microsoft 管理デスクトップ デバイスへのアクセスに必要なパスワードです。
更新プログラムの展開 | ビジネス (WUfB) の Windows Update を使用すると、ソフトウェアの更新の段階的な展開を実行できます。IT 管理者は、展開のリング ポリシーの設定を変更できません。リング ベースの展開の詳細については、[更新プログラムを処理する方法](../working-with-managed-desktop/updates.md)を参照してください。
「遠隔測定」 | 商用既知の識別子の下にある、強化された診断データをマイクロソフトに提供するのには、デバイスが設定されます。お客様の一般的なデータ保護規制 (GDPR) 地域では、エンド ・ ユーザー減らすことができます提供されている診断データのレベル。、これをカスタマイズすることができますが、サービスを削減することがあります。詳細についてを参照してください[、組織の診断データを Windows を構成します](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。

## <a name="advanced-policies"></a>高度なポリシー

 これらは、規制の多い業界よりセキュリティで保護されたまたはロック ダウンの環境用に構成する追加のポリシーです。

 ポリシー | 説明
 --- | ---
 高度な機能 | Windows 情報保護 (WIP) と Azure の情報の保護 (AIP) は、のみ、特定のユーザーまたはアプリケーションとサービスの一部へのアクセスを許可することにより、企業データを保護するために使用されます。詳細については、次を参照してください。<br>- [Windows の情報保護を使用してエンタープライズ データを保護します。](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)<br>- [Azure の情報保護クライアント管理者ガイド](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)<br>- [マイクロソフトは、付属のデスクトップのセキュリティを管理](#security-addendum)

 ## <a name="security-addendum"></a>付属のセキュリティ

 このセクションでは、標準的な Microsoft 管理デスクトップ ポリシーに追加導入されるポリシーについて説明します。[既定のポリシー](#default-policies)では、標準的なポリシーが一覧表示されます。この構成は、金融サービスおよび注意の規制の多い業界で設計されています: ユーザーの生産性を維持しながら、最も安全な態勢を最適化します。

公開された**セキュリティ基準**への変更、[**ネットワークの選択 UI を表示しない**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowslogon#windowslogon-dontdisplaynetworkselectionui)設定を使用できなくなります。

 ### <a name="additional-security-policies"></a>追加のセキュリティ ポリシー

 規制の厳しい業界のセキュリティを強化するには、これらのポリシーが追加されます。 
 - **アプリケーションの一覧を許可する**: アプリケーションは、Microsoft 管理デスクトップ デバイス上で実行する組織によって信頼されている必要があります。これは、ロック ダウンした環境を提供します。Onboarded を使用する必要がある任意のアプリケーションは、Microsoft デスクトップ操作の管理チームに伝えなければなりません。詳細については、 [Windows Defender のデバイスの保護](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)を参照してください。
 - **セキュリティの監視**: マイクロソフトでは、[高度な脅威保護の Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)を使用してデバイスを監視します。マイクロソフトは、お客様に通知、脅威が検出される場合は、デバイスを特定し、リモートで問題を修正します。 
 - **ガードの悪用**: は、どうすれば管理されたデスクトップの Microsoft デバイスが、最新のセキュリティ更新プログラム、オペレーティング システムとアプリケーションの両方で常に保護されていること[ビジネスのための Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)を使用します。脆弱性に対する攻撃のガードは、これらの設定で構成されます。

 設定 | ポリシー
 --- | ---
 フラグの資格情報が Windows のローカル セキュリティ機関サブシステムから盗む | 監査のみ
 Office アプリケーションを他のプロセス内に挿入します。 | 監査のみ
 Office アプリケーションとマクロを実行可能なコンテンツを作成します。 | ブロック
 子プロセスを起動する Office アプリケーション | 監査のみ
 Win32 は、Office のマクロ コードからインポートします。 | ブロック
 Js、vbs、ps/マクロのコードを難読化 | ブロック
 Js と vbs のペイロードの実行が (例外なし) をインターネットからダウンロード | ブロック
 PSExec と WMI のコマンドからのプロセスの作成 | 監査のみ
 USB から実行しているプロセスが信頼されていない、署名されていません。 | ブロック
 実行可能ファイル、流行、年齢、または信頼されたリストの条件に一致しません。 | 監査のみ
 電子メールから削除する実行可能なコンテンツの実行 | ブロック
 Ransomware の高度な保護 | 監査のみ









