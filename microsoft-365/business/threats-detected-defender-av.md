---
title: Microsoft Defender ウイルス対策によって検出された脅威
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Microsoft Defender ウイルス対策が、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威から Windows デバイスを保護する方法について説明します。
ms.openlocfilehash: 1653aef6967cdf76e6e19acda158fb29758280a8
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870901"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策によって検出された脅威

Microsoft Defender ウイルス対策は、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威から Windows デバイスを保護します。

- ウイルスは通常、デバイスまたはネットワーク上の他のファイルにコードを添付して拡散し、感染したプログラムが正しく動作しない可能性があります。
- マルウェアには、悪意のあるファイル、アプリケーション、コードが含まれています。このコードは、破損を引き起こしたり、デバイスの通常の使用を妨害する可能性があります。 また、マルウェアは承認されていないアクセスを許可したり、システム リソースを使用したり、パスワードとアカウント情報を盗んだり、コンピューターからロックアウトして身代金を求めるなどできます。
- スパイウェアは、Web 閲覧アクティビティなどのデータを収集し、そのデータをリモート サーバーに送信します。
 
脅威からの保護を提供するために、Microsoft Defender ウイルス対策はいくつかの方法を使用します。 これらの方法には、クラウドによる保護、リアルタイム保護、および専用の保護更新が含まれます。

- クラウドによる保護は、新しい脅威や新たな脅威をほぼ瞬時に検出してブロックするのに役立ちます。
- 常時有効なスキャンでは、ファイルとプロセスの動作の監視、および他の手法 (リアルタイム保護とも呼ばれる) *を使用します*。
- 専用の保護更新プログラムは、機械学習、人的および自動化されたビッグ データ分析、および詳細な脅威に対する抵抗に関する調査に基づいて行います。 

マルウェアと Microsoft Defender ウイルス対策の詳細については、次の記事を参照してください。 

- [マルウェアと他の&について](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft がマルウェアや望ましくない可能性のあるアプリケーションを特定する方法](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10 の次世代保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Microsoft 以外のウイルス対策ソリューションを使用すると、何が起こりますか? 

Microsoft Defender ウイルス対策はオペレーティング システムの一部であり、Windows 10 を実行しているデバイスで有効になります。 ただし、Microsoft 以外のウイルス対策ソリューションを使用しているが [、Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用していない場合、Microsoft Defender ウイルス対策は自動的に無効モードになります。  

無効モードの場合でも、ユーザーとユーザーは、スケジュールされたスキャンまたはオンデマンド スキャンで Microsoft Defender ウイルス対策を使用して脅威を特定できます。ただし、Microsoft Defender ウイルス対策は次の機能を使用しなくなりました。

- は、既定のウイルス対策アプリとして使用されます。
- ファイルをアクティブにスキャンして脅威を検出します。
- 脅威を修復または解決します。

Microsoft 以外のウイルス対策ソリューションをアンインストールすると、Microsoft Defender ウイルス対策は自動的にアクティブ モードに入り、Windows デバイスを脅威から保護します。

> [!TIP]
> - Microsoft 365 を使用している場合は、プライマリ ウイルス対策ソリューションとして Microsoft Defender ウイルス対策の使用を検討してください。 統合は、より優れた保護を提供します。 Microsoft [Defender ウイルス対策と Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)を一緒に参照してください。
> - Microsoft 以外のウイルス対策ソリューションを使用している場合でも、Microsoft Defender ウイルス対策を最新の状態に保つ必要があります。

## <a name="what-to-expect-when-threats-are-detected"></a>脅威が検出された場合の期待される機能

Microsoft Defender ウイルス対策によって脅威が検出されると、次のことが発生します。

- ユーザーは Windows [で通知を受け取る](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)。 
- 検出は、Windows セキュリティ アプリの [保護 [の履歴]](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) **ページに一覧表示** されます。  
- [Windows 10](secure-win-10-pcs.md)デバイスをセキュリティで保護し [、Intune](/mem/intune/enrollment/windows-enrollment-methods)に登録したデバイスが組織に 800 台以下の場合は <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">、Microsoft 365</a>管理センターの [脅威とウイルス対策] ページに脅威の検出と分析情報が表示されます。このページには、ホーム ページの **Microsoft Defender** ウイルス対策カード (または、[正常性の脅威]  >  **&** ウイルス対策を選択してナビゲーション ウィンドウから) からアクセスできます。

    組織に Intune に登録されているデバイスが 800 を超える場合は、[脅威とウイルス対策] ページではなく[、Microsoft Endpoint Manager](/mem/endpoint-manager-overview)から脅威の検出と分析情報を表示するように求められます。
 
    > [!NOTE]
    > Microsoft **Defender ウイルス** 対策カードと **脅威** とウイルス対策ページは段階的に展開されています。そのため、すぐにアクセスできない場合があります。

ほとんどの場合、ユーザーはそれ以上のアクションを実行する必要はありません。 デバイスで悪意のあるファイルやプログラムが検出されるとすぐに、Microsoft Defender ウイルス対策によってブロックされ、実行が阻止されます。 さらに、新しく検出された脅威がウイルス対策およびマルウェア対策エンジンに追加され、他のデバイスやユーザーも保護されます。  

悪意のあるファイルの削除の承認など、ユーザーが実行する必要があるアクションがある場合、ユーザーが受け取った通知にそれが表示されます。 Microsoft Defender ウイルス対策がユーザーに代わって実行するアクションや、ユーザーが実行する必要がある操作の詳細については、「保護の履歴」を [参照してください](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。 IT プロフェッショナル/管理者として脅威の検出を管理する方法については、「検出された脅威を確認してアクションを実行する」を [参照してください](review-threats-take-action.md)。

さまざまな脅威について詳しくは <a href="https://www.microsoft.com/wdsi/threats" target="_blank">、Microsoft セキュリティ</a>インテリジェンスの脅威サイトをご覧ください。このサイトでは、次のアクションを実行できます。 

- トップの脅威に関する現在の情報を表示します。
- 特定の地域の最新の脅威を表示します。
- 特定の脅威に関する詳細については、脅威の脅威を検索します。

## <a name="related-content"></a>関連コンテンツ

[セキュリティで保護された Windows 10 デバイス](secure-windows-10-devices.md) (記事)\
[Microsoft Defender ウイルス対策を評価](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) する (記事)\
[リアルタイムおよびクラウドによるウイルス対策保護を有効にする](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) 方法 (記事)\
[Windows セキュリティ アプリで Microsoft Defender ウイルス](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) 対策を有効にし、使用する方法 (記事)\
[グループ ポリシーを使って Microsoft Defender ウイルス対策を有効にする方法](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (記事)\
[ウイルス対策定義を更新する方法](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (記事)\
[分析のためにマルウェアとマルウェア以外のマルウェアを Microsoft に送信する](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) 方法 (記事)