---
title: Microsoft Defender ウイルス対策によって検出された脅威
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Microsoft Defender ウイルス対策が、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威から Windows デバイスを保護する方法について説明します。
ms.openlocfilehash: fdaab824ecd64742bb8b912dfde35fa15387cd0a
ms.sourcegitcommit: c216ffa5da8f431e4380bb133a234ae7d94144c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2022
ms.locfileid: "65893503"
---
# <a name="overview-of-threat-protection-by-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策による脅威保護の概要

Microsoft Defender ウイルス対策は、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威から Windows デバイスを保護します。

- ウイルスは通常、デバイスまたはネットワーク上の他のファイルにコードを添付することで拡散し、感染したプログラムが正しく動作しない可能性があります。
- マルウェアには、デバイスの通常の使用に損害を与え、中断する可能性がある悪意のあるファイル、アプリケーション、コードが含まれます。 また、マルウェアは不正アクセスを許可したり、システム リソースを使用したり、パスワードやアカウント情報を盗んだり、コンピューターからロックアウトしたり、身代金を要求したりすることもできます。
- スパイウェアは、Web 閲覧アクティビティなどのデータを収集し、リモート サーバーにデータを送信します。
 
脅威の保護を提供するために、Microsoft Defender ウイルス対策ではいくつかの方法を使用します。 これらの方法には、クラウド配信の保護、リアルタイム保護、および専用の保護更新プログラムが含まれます。

- クラウド配信の保護は、新しい脅威や新しい脅威のほぼ瞬時の検出とブロックを提供するのに役立ちます。
- 常時オン スキャンでは、ファイルとプロセス動作の監視やその他の手法 ( *リアルタイム保護* とも呼ばれます) が使用されます。
- 専用の保護更新プログラムは、機械学習、人間と自動化されたビッグ データ分析、および詳細な脅威耐性の研究に基づいています。 

マルウェアと Microsoft Defender ウイルス対策の詳細については、次の記事を参照してください。 

- [マルウェア&他の脅威について](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft がマルウェアと望ましくない可能性があるアプリケーションを識別する方法](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10 での次世代保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Microsoft 以外のウイルス対策ソリューションが使用されるとどうなりますか? 

Microsoft Defender ウイルス対策はオペレーティング システムの一部であり、Windows 10 を実行しているデバイスで有効になっています。 ただし、Microsoft 以外のウイルス対策ソリューションを使用していて、 [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) を使用していない場合は、Microsoft Defender ウイルス対策が自動的に無効モードになります。  

無効モードの場合でも、ユーザーと顧客は、スケジュールされたスキャンまたはオンデマンド スキャンに Microsoft Defender ウイルス対策を使用して脅威を特定できます。ただし、Microsoft Defender ウイルス対策は次の操作を行いません。

- は、既定のウイルス対策アプリとして使用されます。
- ファイルを積極的にスキャンして脅威を検出します。
- 脅威を修復または解決します。

Microsoft 以外のウイルス対策ソリューションをアンインストールすると、Microsoft Defender ウイルス対策は自動的にアクティブ モードになり、Windows デバイスを脅威から保護します。

> [!TIP]
> - Microsoft 365 を使用している場合は、主なウイルス対策ソリューションとして Microsoft Defender ウイルス対策を使用することを検討してください。 統合により、より優れた保護を提供できます。 Microsoft [Defender ウイルス対策と Office 365 に関](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)するページを参照してください。
> - Microsoft 以外のウイルス対策ソリューションを使用している場合でも、Microsoft Defender ウイルス対策を最新の状態に保つようにしてください。

## <a name="what-to-expect-when-threats-are-detected"></a>脅威が検出されたときに何を期待するか

Microsoft Defender ウイルス対策によって脅威が検出されると、次のことが発生します。

- ユーザーは [Windows で通知を](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)受け取ります。 
- 検出は、[**保護履歴**] ページの [Windows セキュリティ アプリ](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)に一覧表示されます。  
- [Windows 10 デバイスをセキュリティで保護](../admin/setup/secure-win-10-pcs.md)して [Intune に登録し](/mem/intune/enrollment/windows-enrollment-methods)、組織に登録されているデバイスが 800 台以下の場合は、[**脅威とウイルス対策**] ページの <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>に脅威の検出と分析情報が表示されます。脅威の検出と分析情報は、[**ホーム**] ページの **Microsoft Defender ウイルス対策** カードからアクセスできます (または、[**正常性** > **脅威&ウイルス対策**] を選択してナビゲーション ウィンドウからアクセスできます)。

    組織に 800 台を超えるデバイスが Intune に登録されている場合は、[**脅威とウイルス対策**] ページではなく [、Microsoft Endpoint Manager](/mem/endpoint-manager-overview) からの脅威の検出と分析情報を表示するように求められます。
 
    > [!NOTE]
    > **Microsoft Defender ウイルス対策** カード **と脅威とウイルス対策** のページは段階的にロールアウトされているため、すぐにアクセスできない可能性があります。

ほとんどの場合、ユーザーはそれ以上のアクションを実行する必要はありません。 デバイスで悪意のあるファイルまたはプログラムが検出されるとすぐに、Microsoft Defender ウイルス対策によってブロックされ、実行されなくなります。 さらに、新しく検出された脅威がウイルス対策エンジンとマルウェア対策エンジンに追加され、他のデバイスやユーザーも保護されます。  

悪意のあるファイルの削除を承認するなど、ユーザーが実行する必要があるアクションがある場合は、受信した通知にそのアクションが表示されます。 Microsoft Defender ウイルス対策がユーザーの代わりに実行するアクション、またはユーザーが実行する必要があるアクションの詳細については、「 [保護履歴](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)」を参照してください。 IT プロフェッショナル/管理者として脅威検出を管理する方法については、「 [検出された脅威を確認してアクションを実行](m365bp-review-threats-take-action.md)する」を参照してください。

さまざまな脅威の詳細については、次の操作を実行できる <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft セキュリティ インテリジェンス脅威サイト</a>を参照してください。 

- 上位の脅威に関する現在の情報を表示します。
- 特定のリージョンの最新の脅威を表示します。
- 特定の脅威の詳細については、脅威百科事典を検索してください。

## <a name="related-content"></a>関連コンテンツ

[セキュリティで保護された Windows デバイス](/misc/m365bp-secure-windows-devices) (記事)\
[Microsoft Defender ウイルス対策の評価](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (記事)\
[リアルタイムおよびクラウド配信のウイルス対策保護を有効にする方法](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (記事)\
[Windows セキュリティ アプリから Microsoft Defender ウイルス対策を有効にして使用する方法](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (記事)\
[グループ ポリシーを使用して Microsoft Defender ウイルス対策を有効にする方法](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (記事)\
[ウイルス対策定義を更新する方法](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (記事)\
[分析のためにマルウェアと非マルウェアを Microsoft に送信する方法](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (記事)