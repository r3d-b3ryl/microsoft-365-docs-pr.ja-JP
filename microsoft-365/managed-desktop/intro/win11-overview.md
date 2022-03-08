---
title: Microsoft マネージド デスクトップと Windows 11
description: サービスで Windows 11 を使用できる方法と時間
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 494f147dad24b8c668fcb8adfc9b8a845a5fbe8f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317179"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft マネージド デスクトップと Windows 11

Windows 11 の発表後、Windows デバイスを最新の状態に保つ取り組みの一環として、Windows 1 Windows 10 1 の移行の計画を開始した可能性があります。

この記事では、重要な考慮事項と、Microsoft Managed Desktop が環境でのスムーズな移行をサポートする方法について説明します。 11 自体のWindowsについては、「Windows [11 の概要」を参照してください](/windows/whats-new/windows-11)。

Microsoft Managed Desktop デバイスにインストールされている Windows 11 を取得する具体的な手順については、「プレビューとテスト Windows [11 with Microsoft Managed Desktop](../working-with-managed-desktop/test-win11-mmd.md)」を参照してください。

## <a name="timeline-for-windows-10-and-windows-11"></a>11 のWindows 10とWindowsタイムライン

Windows 11 は、2021 年 10 月 4 日に一般提供になりました。 コンシューマーおよびエンタープライズ展開の準備が整い、完全にサポートされているプラットフォームです。

2023 年 1 月から、すべての Microsoft Managed Desktop デバイスの展開のスケジュール設定を開始します。 ただし、11 より早く 11 を展開する場合は、Windowsサポートを提供します。 管理者に相談し、技術的な準備とビジネス上の考慮事項に基づいて、テナントごとに移行計画を開発して実装する方法をアドバイスします。

Microsoft Managed Desktop は、エンタープライズ サポートのWindows 10まで、引き続き並行してサポートを行います。 ライフ [サイクルWindows 10については、「リリース情報](/windows/release-health/release-information)」を参照してください。

## <a name="assessing-pre-release-versions-of-windows-11"></a>11 のプレリリース バージョンWindowsする

Microsoft Managed Desktop デバイスの 95% 以上が、11 を使用Windowsです。 実稼働展開の前にテスト デバイスでアップグレードを試してみる必要がある場合があります。 11 のシステムWindowsの詳細については、「[11 の要件Windows参照してください](/windows/whats-new/windows-11-requirements)。

Microsoft Managed Desktop デバイスの場合、デバイスを [11 テスト Windowsグループに追加できます](/microsoft-365/managed-desktop/working-with-managed-desktop/test-win11-mmd?view=o365-worldwide#add-devices-to-the-windows-11-test-group)。 このグループは、Microsoft Windowsベースライン構成と共に、11 の一般可用性ビルドを受け取ります。 デバイス グループに追加したら、デバイスが新しい設定を受け取り、11 から 11 までWindowsします。

Microsoft Managed Desktop で管理されていないデバイスの場合は、エンドポイント マネージャー 11 の展開Windows[](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/endpoint-manager-simplifies-upgrades-to-windows-11/ba-p/2771886)できます。 デバイスが 11 以降Windowsし、Microsoft Managed Desktop に登録している場合、デバイスは 11 以降に戻Windows 10。

## <a name="support-for-pre-release-windows-11-devices"></a>11 台のデバイスのWindowsサポート

一般提供前にWindows 11 テストを選択した場合、デバイスにプレビュー ビルドがインストールされている可能性があります。

この状態の Microsoft Managed Desktop デバイスは、11 の汎用Windows提供されません。 ただし、発生した問題を解決するためにデバイスは引き続きサポートされます。 Microsoft Managed Desktop は、すべての管理対象デバイスでセキュリティ上の脅威を監視し、デバイスが 11 のプレビュー ビルドを実行している場合に関係なく、Windowsに応答します。

生産性を維持しながら、Windows 11 への移行に取り組むため、プラットフォームで発生した欠陥を報告してください。 優先順位を設定します。

- 11 の広範な展開時にユーザーの生産性をWindows欠陥。
- デバイスのユーザーの生産性をWindows 10欠陥。

## <a name="testing-application-compatibility"></a>アプリケーションの互換性のテスト

アプリケーションの互換性は、生産性が低下する可能性があるため、プラットフォームの移行で最も一般的な懸念事項の 1 つです。 アプリを 11 から 11 にスムーズに移行できると確信するために、いくつかの予防的および対応的なWindowsしています。

### <a name="proactive-measures"></a>予防的な対策

次に、予防的な対策を示します。

| 予防的な対策 | 説明 |
| ----- | ----- |
| 一般的なアプリ | Microsoft では、11 のビルドに展開されている最も一般的なエンタープライズ Windowsテストします。 テスト中に検出された問題を解決するために、外部のソフトウェア発行元および内部製品チームと作業します。 プロアクティブな互換性テストの取り組みの詳細については、「 [Application Compatibility blog」を参照してください](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)。
| 基幹業務アプリ | [Test Base](https://www.microsoft.com/en-us/testbase) は、アプリの発行元と IT 管理者が、Microsoft がセキュリティで保護された Azure 環境で Windows 11 ビルドを実行している仮想マシンで実行するためのアプリとテスト ケースの提出に使用できるリソースです。<br><br>各テスト実行の結果、テスト分析、回帰分析は、プライベート Azure ポータルで利用できます。 Microsoft Managed Desktop は、アプリの使用状況と信頼性データに基づく検証のために、業務上のアプリの優先順位を設定するのに役立ちます。 Test Base の詳細については、「Test [Base for Microsoft 365」 を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566)。 |

### <a name="reactive-measures"></a>反応性メジャー

テスト環境または実稼働環境でアプリの互換性の問題が発生した場合は、サポート要求を開いて無料のサポートを [受け取ります](/microsoft-365/managed-desktop/working-with-managed-desktop/test-win11-mmd?view=o365-worldwide#report-issues)。

11 Windowsサポートには、最新のオペレーティング システム ビルドで実行される次のアプリの機能が含まれています。

- Office
- Microsoft Edge
- Teams
- line-of-business アプリケーション

Microsoft App Assure は、必要に応じてアプリの互換性の問題に優先順位を付け、解決するためにアプリの発行元に直接関与します。
