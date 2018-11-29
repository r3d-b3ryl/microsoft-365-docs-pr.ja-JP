---
title: Microsoft マネージド デスクトップのセキュリティ
description: ''
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 0ea0bbc6a8055ee8459fadd85a6fa4ddac14bdb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869624"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのセキュリティ

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

多数の Microsoft テクノロジを使用すると、ことができます、マイクロソフトの管理されたデスクトップのデバイスが安全であることとを管理されたデスクトップの Microsoft セキュリティ ・ オペレーション ・ チームを防ぐため、検出、でき、高度な脅威への応答を確認します。サードパーティ製のセキュリティ製品、アプリケーション、およびサービスは許可されていません。マイクロソフトは、識別情報、ネットワーク、デバイスを確認する標準的なポリシーの基準を適用し、企業のデータがセキュリティで保護し、保護します。

これらのセキュリティ設定のカテゴリは、次のセクションに記載されています。

- [データのセキュリティ](#data-security)に格納され、Azure のセキュリティの配置の要件を満たすようにして、データ
- [デバイスのセキュリティ](#device-security): セキュリティで保護されたようにして、管理されたデスクトップの Microsoft のデバイスは、
- [Id のセキュリティ](#identity-security): さらされないようにして、最新のワークプ レース内のユーザー
- [ネットワーク セキュリティ](#network-security): ようにして、社内リソースへのセキュリティで保護されたアクセス
- [情報セキュリティ](#information-security): セキュリティで保護されたようにして、企業のデータは、
- [アクセスの権限を持つアカウント](#privileged-account-access)のアクセスを制限する方法

## <a name="data-security"></a>データ セキュリティ

テナントから送信されるデータは、米国でホストされている Microsoft のテナントに Azure の SQL データベースに格納されます。データが格納され、Azure のセキュリティの配置の要件を満たしています。 

詳細については、 [Microsoft Azure のセキュリティ](https://www.microsoft.com/TrustCenter/Security/azure-security)を参照してください。

このリストは、Microsoft と、テナントの間で転送されるデータの種類をまとめたものです。 

- テナントにマイクロソフトから
    - グループ名
    - セキュリティ ポリシーの構成
    - デバイスの注文
    - ユーザーのアカウント (msadmin、mstest、マイクロソフトの管理の Desktop_soc_ro、マイクロソフトの管理 Desktop_wdgsoc)
    - 上記の 4 つのユーザーに E5 のライセンスの割り当て
    - Windows 更新プログラムの呼び出し回数のポリシーを更新します。
    - 今後、さらに機能が開発する他の種類のアプリケーション、ポリシー、および設定を含む構成内容の転記を許可します。
- マイクロソフト、テナントから
    - デバイスの更新プログラム、使用状況および信頼性データ
    - アプリケーションの展開と信頼性のデータ
    - 更新プログラムとセキュリティ ポリシーの配置のデータ
    - デバイスに割り当てられているユーザー



## <a name="device-security"></a>デバイスのセキュリティ

セキュリティ侵害を防ぐためには、Microsoft 管理されたデスクトップのすべてのデバイスが正常な状態とセキュリティで保護されたことを確認するのには重要ですが。問題のあるデバイスを検出し、できるだけ早期にリスクを軽減することを確認しても同様に重要です。

管理されたデスクトップの Microsoft のデバイスは、信頼できる、正常なセキュリティで保護されたことを確認するのには提供されるサービスを次の表に一覧します。

サービス | 説明
--- | ---
ウイルス対策 | 私たちことを確認します。<br>-Windows Defender のウイルス対策のインストールし、構成<br>-Windows Defender のウイルス対策定義が最新の状態
フル ボリューム暗号化 |    Windows BitLocker は、Microsoft 管理デスクトップ デバイスのデータの暗号化ソリューションです。<br><br>組織がサービスに onboarded と、デバイスはデバイスがスリープ モードに切り替える場合は、ローカル データに不正アクセスを防止するのには Windows BitLocker と組み込み信頼プラットフォーム モジュール (TPM) を使用して暗号化されます。 
"Monitoring/監視" |    Windows Defender 高度な脅威保護 (Windows Defender の ATP) は、マイクロソフトの管理されたデスクトップのすべてのデバイス向けのソリューションを監視するセキュリティ上の脅威です。Windows Defender の分析ツールにより、企業を検出し、調査し、企業ネットワーク内の高度な脅威に対応します。詳細についてを参照してください[の高度な脅威保護の Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 。 
ソフトウェアの更新 |  マイクロソフトは、マイクロソフトの管理されたデスクトップのデバイスが、最新のセキュリティ更新プログラム、Windows、Office、Windows Update を使用して、ビジネスので常に保護されていることを確認します。
[回復] |  企業のデータは、ビジネスの OneDrive に格納され、Microsoft 管理デスクトップ デバイスに簡単に復元できます。詳細についてを参照してください[ビジネスのための OneDrive です](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US)。 



## <a name="identity-security"></a>Id のセキュリティ

アイデンティティおよびアクセス管理では、企業の資産とビジネス ・ クリティカルなデータを保護します。Azure Active Directory (AD の Azure) がクラウドで id サービスを提供し、確実に信頼できるユーザーのみを有効にするクラウド ベースの認証は Microsoft 管理デスクトップ デバイスから社内リソースにアクセスできます。

サービス | 説明
--- | ---
エンタープライズ グレードの認証プロバイダー |  マイクロソフトで使用される azure の AD のプレミアム ・ エディションでは、グローバルに分散したデータ センターでホストされている可用性の高いサービスを提供します。サービスは、何十億もの認証を処理するには、1 日に 200 人以上のアクティブなユーザーから、99.9% の SLA を提供します。
バイオ メトリック認証 |  Windows こんにちはでは、ユーザーが自分の顔や PIN、パスワードを忘れたり紛失したり、盗難が発生しにくくすることを使用してログインします。構成する追加の作業が必要です。詳細についてを参照してください[Windows こんにちは](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)。
多要素認証 | Azure の多要素認証は、設置に不正アクセスを防ぐことが携帯電話にも、セルフ サービス パスワード リセットを使用する認証のレベルを提供することによってアプリケーションをクラウドとします。 
標準ユーザーのアクセス許可 |  システムを保護し、セキュリティを強化、ユーザーが割り当てられます標準ユーザーのアクセス許可。これは、Windows の自動操縦装置の標準のエクスペリエンスの一部として割り当てられます。



## <a name="network-security"></a>ネットワークのセキュリティ

お客様は、ネットワークのセキュリティを担当します。 

サービス | 説明
--- | ---
VPN | お客様は、イントラネットの外部企業の限られたリソースを公開することを確認するのには、VPN インフラストラクチャを所有します。<br><br>最低限の条件: Microsoft の管理されたデスクトップには、Windows 10 互換性があり、サポートされている VPN ソリューションが必要です。組織では、VPN ソリューションを必要とする場合は、10 の Windows をサポートしており、パッケージ、および Intune によって展開する必要があります。詳細については、ソフトウェアの発行元に問い合わせてください。<br><br>に関する推奨事項:<br>マイクロソフトは、Intune によってプッシュ VPN プロファイルを簡単に展開されている最新の VPN ソリューションをお勧めします。これは、企業ネットワークにアクセスするのには、常時、シームレスな信頼性、およびセキュリティで保護された方法を提供します。詳細については、Intune での VPN 設定を参照してください。<br>-厚みの VPN クライアント、または従来の VPN クライアントでは、推奨されませんマイクロソフトによってエンドユーザーの環境に影響を与えることができます、マイクロソフトの管理されたデスクトップを使用しているときに。<br>マイクロソフトでは、発信の web トラフィックのパフォーマンスの問題を回避するのには VPN を経由せずにインターネットに直接にはお勧めします。<br>-理想的には、Azure Active ディレクトリのアプリケーション プロキシ、VPN ではなくの使用を推奨します。


## <a name="information-security"></a>情報セキュリティ

お客様は、企業の付加価値の高い資産を保護するためにこれらのオプション サービスを構成することができます。 

サービス | 説明
--- | ---
条件付きアクセス |    デバイスは準拠している場合にのみ、社内のリソースとサービスへのアクセスを許可します。
データ ・ リカバリ  | デバイス上のキーのフォルダーに格納された情報は、Bbusiness の OneDrive にバックアップされます。Microsoft 管理されたデスクトップは、ビジネスのための OneDrive と同期されていないデータの責任ではありません。 
Windows 情報保護 |    [Windows の情報保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)をお勧め高いレベルの情報セキュリティを必要とする企業と[Azure 情報保護します。](https://www.microsoft.com/cloud-platform/azure-information-protection)。 


## <a name="privileged-account-access"></a>特権を持つアカウントのアクセス

今日では、私たちへのアクセス制限 MSAdmin のユーザー資格情報とアプリケーションこれらのメカニズムを使用。

- **演算子**: フルタイムの時間-した Microsoft の社員、米国内にある定期的なバック グラウンドとセキュリティ チェックが完了しました。
- **オペレーター識別情報**: は、Microsoft が設定した基準に従って保護されます。詳細については、[管理するユーザー id およびマイクロソフトのセキュリティで保護されたアクセス](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)を参照してください。 
- **ログ**は、演算子の環境内で、お客様のテナント内で実行されます。ログ データと個人情報は、それぞれの環境内に保持され、環境を通過しません。 

