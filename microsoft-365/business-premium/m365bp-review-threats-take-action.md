---
title: デバイスで検出された脅威を確認し、アクションを実行する
f1.keywords: NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Windows デバイス上のMicrosoft Defender ウイルス対策によって検出された脅威を確認して管理する方法について説明します。
ms.openlocfilehash: dfa76f3a4af903663537c662f7a63b19ab85ba38
ms.sourcegitcommit: a8fbaf4b441b5325004f7a2dacd9429ec9d80534
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2022
ms.locfileid: "65739933"
---
# <a name="review-threats-detected-by-microsoft-defender-antivirus-and-take-action"></a>Microsoft Defender ウイルス対策によって検出された脅威を確認し、アクションを実行する

悪意のあるファイルまたはソフトウェアが検出されるとすぐに、Microsoft Defender ウイルス対策ブロックされ、実行されなくなります。 また、クラウド配信の保護が有効になっていると、新しく検出された脅威がウイルス対策エンジンとマルウェア対策エンジンに追加され、他のデバイスやユーザーも保護されます。

Microsoft Defender ウイルス対策は、次の種類の脅威を検出して保護します。

- デバイス上のウイルス、マルウェア、Web ベースの脅威
- フィッシングの試行
- データ盗難の試行

IT プロフェッショナル/管理者は、[Microsoft 365 管理センターのIntuneに登録されているWindows デバイス間の](/mem/intune/enrollment/device-enrollment)脅威検出に関する情報を表示できます。 次のような概要情報が表示されます。

- ウイルス対策保護が必要なデバイスの数
- セキュリティ ポリシーに準拠していないデバイスの数
- 現在アクティブ、軽減、または解決されている脅威の数

脅威の検出とデバイスに関する特定の情報を表示するには、いくつかのオプションがあります。

- Microsoft 365 管理センターの **[アクティブな脅威**] ページを使用 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">します</a>。 この記事 [の「 **アクティブな** 脅威」ページの脅威検出の管理に関する](#manage-threat-detections-on-the-active-threats-page) ページを参照してください。
- Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で **セキュリティ レポート** を使用します。 この記事の「[Microsoft 365 Defender ポータルでの脅威検出の表示と管理](#view-and-manage-threat-detections-in-the-microsoft-365-defender-portal)」を参照してください。
- Microsoft エンドポイント マネージャーの **[ウイルス対策]** ページを使用 <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">します</a>。 この記事の「[Microsoft エンドポイント マネージャーの脅威検出の管理](#manage-threat-detections-in-microsoft-endpoint-manager)」を参照してください。

詳細については、「[Microsoft Defender ウイルス対策によって検出された脅威](/admin/security-and-compliance/threats-detected-defender-av.md)」を参照してください。

## <a name="manage-threat-detections-on-the-active-threats-page"></a>**[アクティブな** 脅威] ページで脅威の検出を管理する

1. Microsoft 365 管理センターに<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>移動してサインインします。

2. **Microsoft Defender ウイルス対策** カードで、[**アクティブな脅威の表示**] を選択します。 (または、ナビゲーション ウィンドウで [**正常性** > ] を選択します。**脅威&ウイルス対策**.)

3. [ **アクティブな脅威** ] ページで、検出された脅威を選択して詳細を確認します。 ポップアップが開き、影響を受けるデバイスなど、その脅威に関する詳細が表示されます。

4. ポップアップで、使用可能なアクション ( **更新ポリシー**、 **ウイルス対策の更新**、 **クイック スキャンの実行** など) を表示するデバイスを選択します。

### <a name="actions-you-can-take"></a>実行できるアクション

特定の脅威やデバイスに関する詳細を表示すると、推奨事項と実行できる 1 つ以上のアクションが表示されます。 次の表では、表示される可能性があるアクションについて説明します。<br><br>

| アクション | 説明 |
|--|--|
| 保護を構成する | 脅威保護ポリシーを構成する必要があります。 リンクを選択して、ポリシー構成ページに移動します。<br><br>お困りの際は、 [Microsoft Intuneのエンドポイント セキュリティ ポリシーを使用したデバイス セキュリティの管理に関するページを参照](/mem/intune/protect/endpoint-security-policy)してください。 |
| ポリシーを更新する | ウイルス対策ポリシーとリアルタイム保護ポリシーを更新または構成する必要があります。 リンクを選択して、ポリシー構成ページに移動します。<br><br>お困りの際は、 [Microsoft Intuneのエンドポイント セキュリティ ポリシーを使用したデバイス セキュリティの管理に関するページを参照](/mem/intune/protect/endpoint-security-policy)してください。 |
| クイック スキャンを実行する | レジストリ キーや既知のWindowsスタートアップ フォルダーなど、マルウェアが登録されている可能性がある一般的な場所に焦点を当てて、デバイスでクイックウイルス対策スキャンを開始します。 |
| フル スキャンを実行する | デバイスで完全なウイルス対策スキャンを開始し、マルウェアが登録される可能性がある一般的な場所に焦点を当て、デバイス上のすべてのファイルとフォルダーを含めます。 結果は[Microsoft エンドポイント マネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)に送信されます。 |
| ウイルス対策を更新する | デバイスがウイルス対策とマルウェア対策の [保護のためにセキュリティ インテリジェンス更新プログラム](https://go.microsoft.com/fwlink/?linkid=2149926) を取得する必要があります。 |
| デバイスの再起動 | Windows 10 デバイスを強制的に 5 分以内に再起動します。<br><br>**大事な：** デバイスの所有者またはユーザーに再起動の通知が自動的に表示されないため、未保存の作業が失われる可能性があります。 |

## <a name="view-and-manage-threat-detections-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで脅威の検出を表示および管理する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、[ **レポート** > **全般** > **セキュリティ レポート**] を選択します。

3. **[デバイス]** 行まで下にスクロールします。 デバイスで脅威が検出された場合は、この行にその情報が表示されます。

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャーで脅威の検出を管理する

Microsoft エンドポイント マネージャーを使用して、脅威の検出を管理できます。 Windows 10デバイスはIntune (Microsoft エンドポイント マネージャーの一部) [に登録](/mem/intune/enrollment/windows-enrollment-methods)する必要があります。

1. Microsoft エンドポイント マネージャー管理センターに<a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a>移動し、サインインします。

2. ナビゲーション ウィンドウで、[ **エンドポイント セキュリティ**] を選択します。

3. [ **管理**] で、[ **ウイルス対策**] を選択します。 **[概要]**、[**異常なエンドポイントWindows 10**、**検出されたマルウェアWindows 10** など、いくつかのタブが表示されます。

4. 使用可能なタブの情報を確認し、必要なアクションを実行します。

たとえば、検出 **されたマルウェアのWindows 10** タブにデバイスが一覧表示されているとします。デバイスを選択すると、**再起動**、**クイック スキャン**、**フル スキャン**、**同期**、**更新署名** など、特定のアクションを使用できます。 そのデバイスのアクションを選択します。

次の表では、Microsoft エンドポイント マネージャーに表示される可能性があるアクションについて説明します。<br><br>

| アクション | 説明 |
|--|--|
| Restart | Windows 10 デバイスを強制的に 5 分以内に再起動します。<br><br>**大事な：** デバイスの所有者またはユーザーに再起動の通知が自動的に表示されないため、未保存の作業が失われる可能性があります。 |
| クイック スキャン | レジストリ キーや既知のWindowsスタートアップ フォルダーなど、マルウェアが登録されている可能性がある一般的な場所に焦点を当てて、デバイスでクイックウイルス対策スキャンを開始します。 結果は[Microsoft エンドポイント マネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)に送信されます。 |
| フル スキャン | デバイスで完全なウイルス対策スキャンを開始し、マルウェアが登録される可能性がある一般的な場所に焦点を当て、デバイス上のすべてのファイルとフォルダーを含めます。 結果は[Microsoft エンドポイント マネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)に送信されます。 |
| 同期 | デバイスがIntune (Microsoft エンドポイント マネージャーの一部) でチェックインする必要があります。 デバイスがチェックインすると、デバイスに割り当てられている保留中のアクションまたはポリシーがデバイスに受信されます。 |
| 署名を更新する | デバイスがウイルス対策とマルウェア対策の [保護のためにセキュリティ インテリジェンス更新プログラム](https://go.microsoft.com/fwlink/?linkid=2149926) を取得する必要があります。 |

> [!TIP]
> 詳細については、「 [デバイスのリモート アクション」を参照してください](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)。

## <a name="how-to-submit-a-file-for-malware-analysis"></a>マルウェア分析のためにファイルを送信する方法

マルウェアが見つからない、または誤って分類されたと思われるファイルがある場合は、そのファイルを Microsoft に送信してマルウェア分析を行うことができます。 ユーザーと IT 管理者は、分析のためにファイルを送信できます。 にアクセスしてください [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="see-also"></a>関連項目

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)

[Microsoft Defender for Businessの概要](../security/defender-business/mdb-overview.md) (Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premiumのお客様に展開されます)
