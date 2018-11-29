---
title: Microsoft 365 Enterprise テスト環境の強化された Office 365 セキュリティ
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: その他の Office 365 のセキュリティ設定を有効にするのに Microsoft 365 エンタープライズ テスト環境に対応するこのテスト ラボ ガイド 』 を使用します。
ms.openlocfilehash: 18e7b682d20c2212ae73783d668250d28b04075f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869266"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境の強化された Office 365 セキュリティ

この資料の手順についてで Microsoft 365 エンタープライズ テスト環境でセキュリティを強化する追加の Office 365 の設定を構成します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。

最小要件で軽量な方法で Office 365 のセキュリティを強化を構成する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。
  
シミュレートされた企業で Office 365 のセキュリティを強化を構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。
  
> [!NOTE]
> Office 365 のセキュリティ強化のテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。 


## <a name="phase-2-configure-increased-office-365-security"></a>フェーズ 2: Office 365 のセキュリティ強化の構成します。

このフェーズでは、Microsoft 365 エンタープライズ テスト環境を Office 365 のセキュリティを向上させるを有効にします。追加の詳細と設定、[セキュリティ強化のため、Office 365 のテナントの構成](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)を参照してください。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>現代の認証をサポートしていないアプリケーションをブロックするのには SharePoint Online を構成します。

現代の認証をサポートしていないアプリケーションの[id とデバイスのアクセスの構成](microsoft-365-policies-configurations.md)、Microsoft 365 サブスクリプションと、デジタル資産のセキュリティ保護の重要な要素である、それらを適用することはできません。 

1. Office 365 ポータルに移動 ([https://portal.office.com](https://portal.office.com)) し、グローバル管理者アカウントを使用して、Office 365 の試用版サブスクリプションにサインインします。
    
  - 軽量の Microsoft 365 テスト環境を使用する場合、ローカル コンピューターからサインインします。
    
  - Microsoft 365 のシミュレートされたエンタープライズ テスト環境を使用する場合は、CLIENT1 バーチャル マシンに接続して、CLIENT1 からサインインし、 [Azure ポータル](https://portal.azure.com)を使用します。
 
2. **Microsoft 365 管理者センター** ] タブで、[**管理**] をクリックします。
3. [新しい**Microsoft 365 管理者センター** ] タブをクリックして**管理センター > SharePoint**。
4. [新しい**SharePoint 管理者センター** ] タブで、**アクセス制御**をクリックします。
5. **現代の認証をサポートしていないアプリケーション**では、下をクリックして**ブロック > OK**。


### <a name="enable-advanced-threat-protection-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、およびマイクロソフトのチームの脅威保護 (ATP) の詳細設定を有効にします。

Office 365 の高度な脅威保護 (ATP) は、機能の Exchange オンライン保護 (EOP) を支援するあなたの電子メールからのマルウェアのままです。分析ツールは、Exchange 管理センター (EAC) またはセキュリティ ポリシーを作成する & ユーザーを保証するためコンプライアンス センターでは、識別できない悪意のある電子メールの添付ファイルまたはリンクのみにアクセスします。詳細については、[高度な脅威保護](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)を参照してください。

1. [お使いのブラウザーの [ **Microsoft 365 管理センター** ] タブをクリックして**管理センター > セキュリティおよびコンプライアンスに関する**。
2. 新しい**セキュリティおよびコンプライアンスに関する**タブをクリックして**脅威の管理 > ポリシー**。
3. **ATP の安全な添付ファイル**をクリックします。
4. **安全な添付ファイル**のウィンドウ**SharePoint、OneDrive、およびマイクロソフトのチームの分析ツールを有効にする**を選択し、[**保存**] をクリックします。

### <a name="enable-anti-malware"></a>マルウェア対策を有効にします。

マルウェアは、ウイルスやスパイウェアで構成されます。その他のプログラムやデータをウイルスに感染し、感染するプログラムを探してコンピューター全体にレプリケートされます。スパイウェアは、個人情報、サインイン情報などの個人データを収集し、マルウェアの作成者に送信するマルウェアを意味します。 

Office 365 は、組み込みのマルウェアやスパムのフィルタ リング機能が悪意のあるソフトウェアからの受信メッセージと送信メッセージを保護するため、迷惑メールから保護するためです。詳細については、 [Office 365 でのスパム対策およびマルウェア対策保護](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)を参照してください。

マルウェア対策のことを確認するには、一般的な添付ファイルの種類を持つファイルの処理を実行しています。

1. **ポリシー**のページに戻るには、ブラウザーの [戻る] ボタンをクリックします。
2. [**マルウェア対策**] をクリックします。
3. という名前の**既定**のポリシーをダブルクリックします。
4. **マルウェア対策ポリシー** ] ウィンドウで、[**設定**] をクリックします。
4. **一般的な添付ファイルの種類のフィルター**] の下をクリックして**の > 保存**。


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a>フェーズ 3: Office 365 のセキュリティ ツールとログを確認します。

このフェーズでは、セキュリティ イベントを通知して、全体的なセキュリティ体制を評価するための組み込みのサービスを確認します。

### <a name="threat-management-dashboard"></a>脅威管理ダッシュ ボード

Office 365 の脅威の管理制御し、管理を組織のデータへのモバイル デバイスへのアクセス、データの損失から組織を保護するため悪意のあるソフトウェアおよび迷惑メールからの受信メッセージと送信メッセージを保護するためにすることができます。ドメインからアカウントを管理ドメインの評判を保護するために、送信者がスプーフィング悪意を持っているかどうかを判断するのには脅威を使用します。詳細については、 [Office 365 のセキュリティとコンプライアンス センターでの脅威の管理](https://docs.microsoft.com/office365/securitycompliance/threat-management)を参照してください。

Office 365 の脅威の管理ダッシュ ボードを表示するのには次の手順を使用します。

1. [お使いのブラウザーの [ **Microsoft 365 管理センター** ] タブをクリックして**管理センター > セキュリティおよびコンプライアンスに関する**。
2. 新しい**セキュリティおよびコンプライアンスに関する**タブをクリックして**脅威の管理 > ダッシュ ボード**。
3. 新しい**ダッシュ ボード**] タブで、ブラウザーで、マルウェアの傾向、洞察、およびダッシュ ボードの他のセクションに注意してください。

### <a name="office-365-cloud-app-security-dashboard"></a>Office 365 のクラウド アプリケーションのセキュリティ ダッシュ ボード

、Office 365 高度なセキュリティの管理と呼ばれていたクラウドのアプリケーションのセキュリティを office 365 では、ポリシーで監視し、調査の結果、実行可能なことができますように、Office 365 サブスクリプションの場合、不審なアクティビティの通知を作成できます。修復アクションです。詳細については、[概要の Office 365 クラウド アプリケーションのセキュリティ](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)を参照してください。

1. [お使いのブラウザーの [ **Microsoft 365 管理センター** ] タブをクリックして**管理センター > セキュリティおよびコンプライアンスに関する**。
2. 新しい**セキュリティおよびコンプライアンスに関する**タブをクリックして**警告 > アラートを高度な管理 > には、Office 365 のクラウド アプリケーションのセキュリティ**。
3. 新しい**クラウド アプリケーションのセキュリティ**] タブでは、ダッシュ ボード ビューと、Office 365 サブスクリプション内でさまざまな活動を監視する既定のポリシーのリストを注意してください。
4. 追跡されているクラウド アプリケーションのセキュリティ活動の概要を表示するダッシュ ボードのアイコンをクリックします。
5. **調査**(眼鏡のアイコン) と、**アクティビティ ・ ログ**を最近使用した記号] の一覧およびその他のアクティビティを参照してください] をクリックします。

### <a name="secure-score"></a>セキュリティで保護されたスコア

1. お使いのブラウザーで新しいタブを作成し、 **securescore.office.com**に移動します。
2. [**ダッシュ ボード] タブ**で、あなたのスコアを向上させるには、現在のセキュリティで保護されたスコアとキュー内のアクションのリストに注意してください。

情報と実稼働環境でこれらの設定を構成するのにはリンクの**情報の保護**の段階では、[構成 Office 365 用にセキュリティを強化する](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)手順を参照してください。

## <a name="next-step"></a>次の手順

追加[情報の保護](m365-enterprise-test-lab-guides.md#information-protection)機能と、テスト環境での機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)

