package com.piyush.mpchartutil;

import com.github.mikephil.charting.components.AxisBase;
import com.github.mikephil.charting.formatter.IAxisValueFormatter;

/**
 * AxisValueFormatter
 * Description: This helps to skip the labels in axises, Can be extended to provide different decorator for values.
 * Date: 10/3/17
 *
 * @author Piyush Agarwal
 */
public class SkipLabelFormatter implements IAxisValueFormatter {

    private int mSkippedCount = 0;

    private int mNoOfLabelsToSkip;

    private int newLabelToSkip;

    public SkipLabelFormatter(int noOfLabelsToSkip) {
        mNoOfLabelsToSkip = noOfLabelsToSkip;
        newLabelToSkip = mNoOfLabelsToSkip;
    }

    @Override
    public String getFormattedValue(float value, AxisBase axis) {
        String label;

        //Always show first one and never show the zeroth one
        if (mSkippedCount == 1) {
            label = getDecoratedValue(value);
        } else if (mSkippedCount - 2 >= newLabelToSkip) {
            label = getDecoratedValue(value);
            newLabelToSkip = newLabelToSkip + mNoOfLabelsToSkip + 1;
        } else {
            label = "";
        }

        mSkippedCount++;
        return label;
    }

    protected String getDecoratedValue(float value) {
        return String.valueOf(value);
    }
}
