---
title: Microsoft Defender のアーキテクチャ要件と計画の概念を確認Office 365
description: Microsoft Defender for Office 365 Microsoft 365 Defenderの技術図は、Microsoft 365またはパイロット環境を構築する前に、Microsoft 365の ID を理解するのに役立ちます。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b0f12d50cd37832a5c9055fdabcffa0968645682
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64498959"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a>Microsoft Defender のアーキテクチャ要件Office 365主な概念について確認する


**適用対象:**
- Microsoft 365 Defender

この記事は[、Microsoft Defender for microsoft Defender の](eval-defender-office-365-overview.md)評価環境をセットアップするプロセスの手順 1/3 Office 365。 このプロセスの詳細については、概要の記事を [参照してください](eval-defender-office-365-overview.md)。

Defender for Office 365を有効にする前に、アーキテクチャを理解し、要件を満たしていることを確認してください。 この記事では、アーキテクチャ、主要な概念、および環境が満たす必要があるExchange Onlineについて説明します。

## <a name="understand-the-architecture"></a>アーキテクチャを理解する

次の図は、サードパーティの SMTP ゲートウェイまたはオンプレミス統合を含む、Office Microsoft Defender for Office のベースライン アーキテクチャを示しています。 ハイブリッド共存シナリオ (つまり、実稼働メールボックスはオンプレミスとオンラインの両方) では、より複雑な構成が必要であり、この記事や評価ガイダンスでは説明しません。

:::image type="content" source="../../media/defender/m365-defender-office-architecture.png" alt-text="Microsoft Defender for microsoft Defender for Office 365" lightbox="../../media/defender/m365-defender-office-architecture.png":::

次の表に、この図を示します。

|コールアウト  |説明  |
|---------|---------|
|1     | 外部送信者のホスト サーバーは、通常、MX レコードのパブリック DNS 参照を実行します。これは、メッセージを中継するターゲット サーバーを提供します。  この参照は、直接 (EXO) Exchange Online、または EXO に対して中継するように構成された SMTP ゲートウェイのいずれかです。  |
|2     | Exchange Online Protection接続をネゴシエートして検証し、メッセージ ヘッダーとコンテンツを検査して、必要な追加のポリシー、タグ付け、または処理を決定します。  |
|3     | Exchange Online Microsoft Defender と統合して、Office 365保護、軽減、修復を提供します。 |
|4     | 悪意のある、ブロックされている、または検疫されていないメッセージが処理され、迷惑メール、メールボックス ルール、または他の設定に関連するユーザー設定が評価され、トリガーされる EXO で受信者に配信されます。 |
|5     | オンプレミスの Active Directory との統合は、Azure AD Connect を使用してメールが有効なオブジェクトとアカウントを同期およびプロビジョニングして、Azure Active Directoryと最終的にExchange Online。 |
|6      | オンプレミス環境を統合する場合は、メール関連の属性、設定、および構成の管理と管理をサポートするために Exchange サーバーを使用してください。 |
|7      | Microsoft Defender for Office 365拡張検出および応答 (XDR) Microsoft 365 Defender信号を共有します。|

オンプレミスの統合は一般的ですが、オプションです。 環境がクラウド専用の場合は、このガイダンスも役立ちます。

## <a name="understand-key-concepts"></a>主要な概念を理解する

次の表では、MDO の評価、構成、および展開を行う際に理解するために重要な重要な概念を示しています。


|概念  |説明 |詳細情報  |
|---------|---------|---------|
|Exchange Online Protection      |    Exchange Online Protection (EOP) は、スパムメールやマルウェアメールから組織を保護するのに役立つクラウドベースのフィルタリング サービスです。 EOP は、ライセンスを含むすべてのMicrosoft 365ライセンスにExchange Online。     |   [Exchange Online Protection の概要](../office-365-security/exchange-online-protection-overview.md)      |
|マルウェア対策保護     |    EXO にメールボックスがある組織は、マルウェアから自動的に保護されます。     |  [EOP のマルウェア対策保護](../office-365-security/anti-malware-protection.md)       |
|スパム対策保護     |   EXO のメールボックスを持つ組織は、迷惑メールやスパム ポリシーから自動的に保護されます。      |  [EOP でのスパム対策保護](../office-365-security/anti-spam-protection.md)       |
|フィッシング対策保護 |  MDO は、スピア フィッシング、捕鯨、ランサムウェア、その他の悪意のあるアクティビティに関連する、より高度なフィッシング対策保護を提供します。   | [Microsoft Defender の追加のフィッシング対策Office 365](../office-365-security/anti-phishing-protection.md)   |
|スプーフィング対策保護     |   EOP には、偽装 (偽造) 送信者から組織を保護するための機能が含まれています。      |   [EOP のスプーフィング対策保護](../office-365-security/anti-spoofing-protection.md)      |
|安全な添付ファイル     |   セーフ添付ファイルは、配信される前に、仮想環境を使用して電子メール メッセージ内の添付ファイルをチェックして "削除" することで、保護の層を強化します。      |   [セーフ用の Microsoft Defender の添付ファイルOffice 365](../office-365-security/safe-attachments.md)      |
|セーフ、SharePoint、OneDriveのMicrosoft Teams     |    さらに、セーフ、SharePoint OneDrive、Microsoft Teams 用の添付ファイルは、クラウド ストレージ リポジトリにアップロードされたファイルに対する保護を強化します。     |  [SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|安全なリンク     | セーフリンクは、受信メール メッセージ内で URL のスキャンと書き換えを提供し、配信またはクリックする前にそれらのリンクの検証を提供する機能です。        |   [セーフ Microsoft Defender for microsoft Defender のリンクOffice 365](../office-365-security/safe-links.md)      |
|    |         |         |

Microsoft Defender for Officeに含まれる機能の詳細については、「[Microsoft Defender for Office 365」を参照してください](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

## <a name="review-architecture-requirements"></a>アーキテクチャ要件を確認する
成功した MDO 評価または実稼働パイロットは、次の前提条件を前提とします。
- すべての受信者メールボックスは現在、Exchange Online。
- パブリック MX レコードは EOP またはサード パーティの SMTP ゲートウェイに直接解決し、受信外部メールを EOP に直接中継します。
- プライマリ 電子メール ドメインは、管理者の *権限* としてExchange Online。
- 必要に応じて、ディレクトリ ベースの *エッジ* ブロック (DBEB) を正常に展開して構成しました。 詳細については、「Use [Directory-Based エッジ](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) ブロック」を参照してください。

> [!IMPORTANT]
> これらの要件が該当しない場合、またはハイブリッド共存シナリオに残っている場合、Office 365 評価用 Microsoft Defender には、このガイダンスで完全に説明されていない複雑な構成または高度な構成が必要な場合があります。

## <a name="siem-integration"></a>SIEM 統合

Microsoft Defender for Office 365 Microsoft Sentinel を統合して、組織全体のセキュリティ イベントをより包括的に分析し、効果的かつ迅速な対応を行うプレイブックを構築できます。 詳細については、「Microsoft [Defender Connectアラート」を参照Office 365](/azure/sentinel/connect-office-365-advanced-threat-protection)。

Microsoft Defender for Office 365アクティビティ管理 API を使用して、他のセキュリティ情報およびイベント管理 (SIEM) ソリューション[Office 365統合することもできます](/office/office-365-management-api/office-365-management-activity-api-reference)。

## <a name="next-steps"></a>次の手順

手順 2/3: [評価環境を有効にする Microsoft Defender for Office 365](eval-defender-office-365-enable-eval.md)

[Microsoft [Defender for Office 365](eval-defender-office-365-overview.md)

[評価とパイロット] [の概要に戻Microsoft 365 Defender](eval-overview.md) 
