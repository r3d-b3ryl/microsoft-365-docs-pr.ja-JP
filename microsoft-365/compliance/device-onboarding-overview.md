---
title: Windows 10 または Windows 11 デバイスを Microsoft 365 にオンボードする概要
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Windows 10 および Windows 11 デバイスを Microsoft 365 にオンボードする
ms.openlocfilehash: ea1038554349b6c035c52bd3d3429d71d7d866bc
ms.sourcegitcommit: 9d563faeaa50b59b0b468dbb373d886e5270f58e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "64387135"
---
# <a name="onboard-windows-10-and-windows-11-devices-into-microsoft-365-overview"></a>Windows 10 および Windows 11 デバイスを Microsoft 365 にオンボードする概要

**適用対象:**

- [エンドポイントのデータ損失防止](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

エンドポイントのデータ損失防止 (エンドポイント DLP) とインサイダー リスク管理では、Windows 10 および Windows 11 デバイスをサービスにオンボードして、監視データをサービスに送信できるようにする必要があります。
 
エンドポイント DLP は、Windows 10 または Windows 11 デバイスを監視し、機密性の高いアイテムが使用および共有されていることを検出します。 これにより、適切に使用および保護されていることを確認し、危険にさらされる可能性のある動作を防止するために必要な可視性と制御を得ることができます。 MicrosoftのすべてのDLP製品の詳細については、「[データ損失防止の概要](dlp-learn-about-dlp.md)」を参照してください。 エンドポイント DLP の詳細については、「[エンドポイント データ損失防止の説明](endpoint-dlp-learn-about.md)」を参照してください。

インサイダー リスク管理では、幅広いサービスとサードパーティの指標を使用して、リスクの高いユーザー アクティビティをすばやく特定、トリアージ、および対処するのに役立ちます。 Microsoft 365 および Microsoft Graph のログを使用することにより、インサイダー リスク管理では、特定のポリシーを定義してリスク指標を特定し、これらのリスクを軽減するためのアクションを実行できます。 詳細については、「[Microsoft 365 のインサイダー リスク管理の詳細](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)」を参照してください。

デバイスのオンボードは、Microsoft 365 と Microsoft Defender for Endpoint (MDE) で共有されます。 既にデバイスを MDE にオンボードしている場合、それらは管理対象デバイス リストに表示され、それらの特定のデバイスをオンボードするために追加の手順は必要ありません。 コンプライアンス センターのオンボード デバイスも、MDE にオンボードします。

## <a name="before-you-begin"></a>はじめに

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプションライセンス

[ここで](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)ライセンス要件を確認してください。

### <a name="permissions"></a>許可

デバイス管理を有効にするには、使用するアカウントが次のいずれかの役割のメンバーでなければなりません。

- グローバル管理者
- セキュリティ管理者
- コンプライアンス管理者

カスタムアカウントを使用してデバイス管理設定を表示する場合は、次のいずれかの役割でなければなりません。

- グローバル管理者
- コンプライアンス管理者
- コンプライアンスデータ管理者
- グローバルリーダー

カスタムアカウントを使用してオンボーディング/オフボーディングページにアクセスする場合は、次のいずれかの役割でなければなりません。

- グローバル管理者
- コンプライアンス管理者

カスタムアカウントを使用してデバイスの監視をオン/オフにする場合は、次のいずれかの役割でなければなりません。

- グローバル管理者
- コンプライアンス管理者

### <a name="prepare-your-windows-devices"></a>Windows デバイスを準備する

オンボードする必要のある Windows デバイスがこれらの要件を満たしていることを確認してください。

1. Windows 10 x64 ビルド 1809 以降または Windows 11 を実行している必要があります。

2. マルウェア対策クライアントのバージョンは 4.18.2110 以降です。 Windows セキュリティ アプリを開いて現在のバージョンを確認し、[設定] アイコンを選択して、[バージョン情報] を選択します。 バージョン番号は、マルウェア対策クライアントのバージョンの下に表示されます。 Windows Update KB4052623 をインストールして、最新のマルウェア対策クライアントのバージョンに更新します。

   > [!NOTE]
   > Windows セキュリティ コンポーネントはいずれもアクティブである必要はありませんが、[リアルタイム保護と動作の監視](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)を有効にする必要があります。

3. 監視対象のデバイスには、次の Windows 10 の Windows 更新プログラムがインストールされています。

   > [!NOTE]
   > これらの更新プログラムは、デバイスをオンボードするための前提条件ではありませんが、重要な問題の修正が含まれているため、製品を使用する前にインストールする必要があります。
   >
    > - Windows 10 1809 の場合 - KB4559003、KB4577069、KB4580390
    > - Windows 10 1903 または 1909 の場合 - KB4559004、KB4577062、KB4580386
    > - Windows 10 2004 の場合 - KB4568831、KB4577063

4. すべてのデバイスは、次のいずれかを満たしている必要があります。

   - [Azure Active Directory (Azure AD) への参加](/azure/active-directory/devices/concept-azure-ad-join)
   - [Hybrid Azure AD への参加](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
   - [AAD の登録](/azure/active-directory/user-help/user-help-register-device-on-network)

5. サポートされているバージョンの Microsoft Office がインストールされ、最新の状態になっています。 最も堅牢な保護とユーザー エクスペリエンスを実現するには、Microsoft 365 Apps バージョン 16.0.14701.0 以降がインストールされていることを確認してください。
> [!NOTE]
   > - Office 365 を実行している場合 - KB 4577063 が必要です。
   > - Microsoft 365 Apps バージョン 2004-2008 の月次エンタープライズ チャネルを使用している場合は、バージョン 2009 以降に更新する必要があります。 現在のバージョンについては「[Microsoft 365 アプリの更新履歴 (日付別の一覧)](/officeupdates/update-history-microsoft365-apps-by-date)」をご覧ください。 既知の問題の詳細については、[2020 年の最新のチャネル リリースのリリース ノート](/officeupdates/current-channel#version-2010-october-27)の「Office スイート」セクションを参照してください。

6. デバイス プロキシを使用してインターネットに接続するエンドポイントがある場合は、「[情報保護のためのデバイス プロキシとインターネット接続設定の構成](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection)」の手順に従います。

## <a name="onboarding-windows-10-or-windows-11-devices"></a>Windows 10 または Windows 11 デバイスのオンボード

デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードしなければなりません。 これらのアクションはどちらも Microsoft 365 コンプライアンスポータルで行われます。

まだオンボードされていないデバイスをオンボードする場合は、適切なスクリプトをダウンロードして、それらのデバイスに展開します。以下のデバイスのオンボード手順に従います。

既に [Microsoft Defender for Endpoint](/windows/security/threat-protection/) にオンボーディングされているデバイスがある場合、それらは管理対象デバイスのリストに表示されます。

この展開シナリオでは、まだオンボードされていない Windows 10 または Windows 11 デバイスをオンボードします。

1. [Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。 [**設定**] > [**デバイス監視を有効にする**] を選択します。

   > [!NOTE]
   > 通常、デバイスのオンボーディングが有効になるまで約60秒かかりますが、Microsoft サポートに連絡するまでに最大 30 分かかります。

2. コンプライアンス センターの設定ページを開き、**[Windows デバイスの監視を有効にする (Turn on Windows device monitoring)]** を選択します。

3. [**デバイス管理**]を選択して、[**デバイス**]リストを開きます。 

> [!NOTE]
> 以前に Microsoft Defender for Endpoint を展開したことがある場合は、そのプロセス中にオンボードされたすべてのデバイスが [**デバイス**] リストに一覧表示されます。それらを再度オンボードする必要はありません。

4. オンボーディングプロセスを開始するには、[**オンボーディング**]を選択します。

5. これらの追加デバイスに導入する方法を[**導入方法**]リストから選択し、**パッケージをダウンロード** します。

6. 以下の表から、従うべき適切な手順を選択します。

トピック | 説明
:---|:---
[グループ ポリシーを使用して Windows 10 または 11 デバイスをオンボードする](device-onboarding-gp.md) | グループ ポリシーを使用して構成パッケージをデバイスに展開します。
[Microsoft Endpoint Configuration Manager を使用した Windows 10 または 11 デバイスのオンボード](device-onboarding-sccm.md) | Microsoft Endpoint Configuration Manager (現在のブランチ) バージョン 1606 または Microsoft Endpoint Configuration Manager (現在のブランチ) バージョン 1602 以前のいずれかを使用して、構成パッケージをデバイスに展開できます。
[モバイル デバイス管理ツールを使用した Windows 10 または 11 デバイスのオンボード](device-onboarding-mdm.md) | モバイル デバイス管理ツールまたは Microsoft Intune を使用して、構成パッケージをデバイスに展開します。
[ローカル スクリプトを使用した Windows 10 または 11 デバイスのオンボード](device-onboarding-script.md) | ローカル スクリプトを使用してエンドポイントに構成パッケージを展開する方法について説明します。
[非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](device-onboarding-vdi.md) | 構成パッケージを使用して VDI デバイスを構成する方法について説明します。

デバイスがオンボードされると、デバイス リストに表示され、アクティビティ エクスプローラーへの監査アクティビティ ログのレポートも開始されます。

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a>DLP 警告管理ダッシュボードでのエンドポイント DLP 警告の表示

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 コンプライアンス センター</a>の [データ損失防止] ページを開き、[アラート] を選択します。

2. エンドポイント DLP ポリシーの警告を表示するには、「[DLP ポリシーの警告を構成および表示する方法](dlp-configure-view-alerts-policies.md)」の手順を参照してください。

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>Activity エクスプローラーでのEndpoint DLPデータの表示

1. Microsoft 365 コンプライアンスセンターでドメインの[データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、Activity エクスプローラーを選択します。

2. エンドポイントデバイスのすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。

   > [!div class="mx-imgBorder"]
   > ![エンドポイント デバイスのアクティビティ エクスプローラー フィルター。](../media/endpoint-dlp-4-getting-started-activity-explorer.png)


## <a name="see-also"></a>関連項目

- [Microsoft 365 のインサイダー リスク管理について](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
- [エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)
- [エンドポイントのデータ損失防止の使用](endpoint-dlp-using.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [Windows 10 マシン用のオンボーディングツールとメソッド](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure AD に参加しているデバイス](/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
