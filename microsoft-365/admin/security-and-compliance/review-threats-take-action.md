---
title: 検出された脅威を確認して対処する
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: デバイス上のユーザーが検出した脅威を確認Microsoft Defender ウイルス対策管理Windows 10します。
ms.openlocfilehash: e0e0613ad7805b8c4bde221aa2192c788fb75106
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324285"
---
# <a name="review-detected-threats-and-take-action"></a>検出された脅威を確認して対処する

悪意のあるファイルやソフトウェアが検出されるとすぐに、Microsoft Defender ウイルス対策ブロックし、実行を妨げる可能性があります。 クラウドによる保護を有効にすると、新たに検出された脅威がウイルス対策エンジンとマルウェア対策エンジンに追加され、他のデバイスやユーザーも保護されます。

Microsoft Defender ウイルス対策検出し、次の種類の脅威から保護します。

- デバイス上のウイルス、マルウェア、および Web ベースの脅威
- フィッシングの試行
- データ盗難の試行

IT プロフェッショナル/管理者は、Intune に登録されている複数のデバイスWindows 10の脅威[](/mem/intune/enrollment/device-enrollment)検出に関する情報を表示Microsoft 365 管理センター。 次のような概要情報が表示されます。

- ウイルス対策保護が必要なデバイスの数
- セキュリティ ポリシーに準拠していないデバイスの数
- 現在アクティブ、軽減、または解決されている脅威の数

脅威の検出とデバイスに関する特定の情報を表示するには、いくつかのオプションがあります。

- [**アクティブなデバイス**] ページの <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">[</a>Microsoft 365 管理センター。 この記事 [の「Active Devices」ページの「脅威検出の管理」](#manage-threat-detections-on-the-active-devices-page) を参照してください。
- [**アクティブな脅威**] ページ <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>。 この記事 [の「アクティブな脅威」ページの「脅威検出の管理」](#manage-threat-detections-on-the-active-threats-page) を参照してください。
- [**ウイルス対策**<a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">] ページMicrosoft エンドポイント マネージャー</a>。 この記事[の「脅威検出の管理」Microsoft エンドポイント マネージャー](#manage-threat-detections-in-microsoft-endpoint-manager)を参照してください。

詳細については、「ユーザーが検出した脅威[」を参照Microsoft Defender ウイルス対策](threats-detected-defender-av.md)。

## <a name="manage-threat-detections-on-the-active-devices-page"></a>[アクティブ なデバイス] ページで **脅威検出を管理** する

以下の手順は、お客様がご利用のお客様Microsoft 365 Business Premium。

1. [サインイン] のMicrosoft 365 管理センターに<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>移動してサインインします。

2. ナビゲーション ページで、[**DevicesActive デバイス]** >  **を選択します**。 アクティブなデバイスの一覧と、保護状態、ウイルス対策 (AV) 保護状態、検出されたアクティブな脅威の数などの詳細が表示されます。

3. デバイスを選択すると、そのデバイスと使用可能なアクションの詳細が表示されます。 フライアウトが開き、ポリシーの更新、ウイルス対策の更新、クイック スキャンの実行、フル スキャンの実行など、推奨事項と使用可能なアクションが表示されます。

## <a name="manage-threat-detections-on-the-active-threats-page"></a>[アクティブな脅威] ページで **脅威検出を管理** する

以下の手順は、お客様がご利用のお客様Microsoft 365 Business Premium。 [Windows 10デバイスをセキュリティで保護し、](../setup/secure-win-10-pcs.md)[Intune に登録する必要があります](/mem/intune/enrollment/windows-enrollment-methods)。

> [!NOTE]
> [**Microsoft Defender ウイルス対策** アクティブな脅威] ページは段階的に展開され、すぐにアクセスできない場合があります。

1. [サインイン] のMicrosoft 365 管理センターに<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>移動してサインインします。

2. [アクティブな **脅威Microsoft Defender ウイルス対策** 表示] を選択 **します**。 (または、ナビゲーション ウィンドウで [正常性] を **選択します。** > **ウイルス対策&脅威**。

3. [アクティブ **な脅威] ページ** で、検出された脅威を選択して詳細を確認します。 フライアウトが開き、影響を受けるデバイスなど、その脅威に関する詳細が表示されます。

4. フライアウトで、デバイスを選択して、ポリシーの更新、ウイルス対策の更新、クイック スキャンの実行など、使用可能なアクションを表示します。

## <a name="actions-you-can-take"></a>実行できるアクション

特定の脅威やデバイスに関する詳細を表示すると、推奨事項と実行できる 1 つ以上のアクションが表示されます。 次の表に、表示される可能性があるアクションについて説明します。<br><br>

| アクション | 説明 |
|--|--|
| 保護の構成 | 脅威保護ポリシーを構成する必要があります。 ポリシー構成ページに移動するリンクを選択します。<br><br>サポートが必要な場合 「[デバイス セキュリティを管理する」を参照](/mem/intune/protect/endpoint-security-policy)してください。Microsoft Intune。 |
| ポリシーを更新する | ウイルス対策ポリシーとリアルタイム保護ポリシーを更新または構成する必要があります。 リンクを選択して、ポリシー構成ページに移動します。<br><br>サポートが必要な場合 「[デバイス セキュリティを管理する」を参照](/mem/intune/protect/endpoint-security-policy)してください。Microsoft Intune。 |
| クイック スキャンの実行 | レジストリ キーや既知のスタートアップ フォルダーなど、マルウェアが登録される可能性がある一般的な場所に焦点を当て、デバイスでWindowsスキャンを開始します。 |
| フル スキャンの実行 | デバイス上で完全なウイルス対策スキャンを開始し、マルウェアが登録される可能性がある一般的な場所と、デバイス上のすべてのファイルとフォルダーを含む場所に注目します。 結果は、ユーザーに[Microsoft エンドポイント マネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| ウイルス対策の更新 | ウイルス対策およびマルウェア対策保護 [のセキュリティ インテリジェンス更新](https://go.microsoft.com/fwlink/?linkid=2149926) プログラムを取得するには、デバイスが必要です。 |
| デバイスの再起動 | 5 分以内Windows 10デバイスを強制的に再起動します。<br><br>**大事な：** デバイスの所有者またはユーザーは自動的に再起動の通知を受け取らなく、保存されていない作業を失う可能性があります。 |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>脅威の検出を管理Microsoft エンドポイント マネージャー

脅威検出を管理Microsoft エンドポイント マネージャーを使用できます。 Windows 10 Intune (デバイス[の](/mem/intune/enrollment/windows-enrollment-methods)一部) に登録する必要Microsoft エンドポイント マネージャー。

1. 管理センターのMicrosoft エンドポイント マネージャーに移動し<a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a>、サインインします。

2. ナビゲーション ウィンドウで、[エンドポイント セキュリティ **] を選択します**。

3. [管理 **] で**、[ウイルス対策] **を選択します**。 [概要] や [不健康なエンドポイントWindows 10検出されたマルウェアなどWindows 10 **表示されます**。

4. 使用可能なタブの情報を確認し、必要な操作を実行します。

たとえば、デバイスが [検出されたマルウェア] タブWindows 10 **表示されると** します。デバイスを選択すると、再起動、クイック スキャン、フル スキャン、同期、更新の署名など、特定のアクションを **使用できます**。 そのデバイスのアクションを選択します。

次の表に、ユーザーに表示される可能性があるアクションMicrosoft エンドポイント マネージャー。<br><br>

| アクション | 説明 |
|--|--|
| Restart | 5 分以内Windows 10デバイスを強制的に再起動します。<br><br>**大事な：** デバイスの所有者またはユーザーは自動的に再起動の通知を受け取らなく、保存されていない作業を失う可能性があります。 |
| クイック スキャン | レジストリ キーや既知のスタートアップ フォルダーなど、マルウェアが登録される可能性がある一般的な場所に焦点を当て、デバイスでWindowsスキャンを開始します。 結果は、ユーザーに[Microsoft エンドポイント マネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| フル スキャン | デバイス上で完全なウイルス対策スキャンを開始し、マルウェアが登録される可能性がある一般的な場所と、デバイス上のすべてのファイルとフォルダーを含む場所に注目します。 結果は、ユーザーに[Microsoft エンドポイント マネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 同期 | デバイスが Intune でチェックインする必要があります (デバイスの一部Microsoft エンドポイント マネージャー)。 デバイスがチェック インすると、デバイスに割り当てられている保留中のアクションまたはポリシーがデバイスに受信されます。 |
| 署名の更新 | ウイルス対策およびマルウェア対策保護 [のセキュリティ インテリジェンス更新](https://go.microsoft.com/fwlink/?linkid=2149926) プログラムを取得するには、デバイスが必要です。 |

> [!TIP]
> 詳細については、「デバイスの [リモート アクション」を参照してください](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)。

## <a name="how-to-submit-a-file-for-malware-analysis"></a>マルウェア分析用にファイルを送信する方法

見つからない、または誤ってマルウェアとして分類されたと思うファイルがある場合は、そのファイルをマルウェア分析のために Microsoft に提出できます。 ユーザーと IT 管理者は、分析用にファイルを提出できます。 Visit [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission).

## <a name="see-also"></a>関連項目

[ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](secure-your-business-data.md)

[Microsoft Defender for Business](../../security/defender-business/mdb-overview.md) の概要 (Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています)