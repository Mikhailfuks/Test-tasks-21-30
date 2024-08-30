tasks 21 
public class ArrayMergeUtil {
    public int[] merge(int[] array1, int[] array2) {
        int[] merged = new int[array1.length + array2.length];
        System.arraycopy(array1, 0, merged, 0, array1.length);
        System.arraycopy(array2, 0, merged, array1.length, array2.length);
        return merged;
    }
}

tasks 22 

import java.util.Arrays;

public class SortUtil {
    public int[] sort(int[] array) {
        Arrays.sort(array);
        return array;
    }
}

tasks 23 

import static org.junit.jupiter.api.Assertions.assertTrue;
import org.junit.jupiter.api.Test;

public class PersonTest {
    @Test
    public void testEquals() {
        Person person1 = new Person("Alice", 30);
        Person person2 = new Person("Alice", 30);
        assertTrue(person1.equals(person2));
    }
}

tasks 24 

public class StringToIntegerUtil {
    public int convert(String str) {
        return Integer.parseInt(str);
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class StringToIntegerUtilTest {
    @Test
    public void testConvert() {
        StringToIntegerUtil util = new StringToIntegerUtil();
        assertEquals(123, util.convert("123"));
    }
}

tasks 25 

import java.text.SimpleDateFormat;
import java.util.Date;

public class DateUtil {
    public String format(Date date) {
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
        return sdf.format(date);
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;
import java.util.Date;

public class DateUtilTest {
    @Test
    public void testFormat() {
        DateUtil dateUtil = new DateUtil();
        assertEquals("2023-08-28", dateUtil.format(new Date(1693248000000L))); // timestamp for 2023-08-28
    }
}

tasks 26 

import java.util.HashSet;

public class DuplicateUtil {
    public boolean hasDuplicates(int[] array) {
        HashSet<Integer> seen = new HashSet<>();
        for (int num : array) {
            if (!seen.add(num)) {
                return true;
            }
        }
        return false;
    }
}

import static org.junit.jupiter.api.Assertions.assertTrue;
import org.junit.jupiter.api.Test;

public class DuplicateUtilTest {
    @Test
    public void testHasDuplicates() {
        DuplicateUtil duplicateUtil = new DuplicateUtil();
        assertTrue(duplicateUtil.hasDuplicates(new int[]{1, 2, 2, 3}));
    }
}

tasks 27 

import java.util.ArrayList;
import java.util.List;

public class FactorUtil {
    public List<Integer> getFactors(int number) {
        List<Integer> factors = new ArrayList<>();
        for (int i = 1; i <= number; i++) {
            if (number % i == 0) {
                factors.add(i);
            }
        }
        return factors;
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class FactorUtilTest {
    @Test
    public void testGetFactors() {
        FactorUtil factorUtil = new FactorUtil();
        assertEquals(List.of(1, 2, 4), factorUtil.getFactors(8));
    }
}

tasks 28

import java.util.Arrays;

public class MedianUtil {
    public double findMedian(int[] array) {
        Arrays.sort(array);
        int n = array.length;
        if (n % 2 == 0) {
            return (array[n / 2 - 1] + array[n / 2]) / 2.0;
        } else {
            return array[n / 2];
        }
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class MedianUtilTest {
    @Test
    public void testFindMedianEven() {
        MedianUtil medianUtil = new MedianUtil();
        assertEquals(3.5, medianUtil.findMedian(new int[]{1, 2, 4, 3}));
    }
    
    @Test
    public void testFindMedianOdd() {
        MedianUtil medianUtil = new MedianUtil();
        assertEquals(3, medianUtil.findMedian(new int[]{1, 3, 2}));
    }
}

tasks 29

public class PrimeUtil {
    public boolean isPrime(int number) {
        if (number <= 1) return false;
        for (int i = 2; i <= Math.sqrt(number); i++) {
            if (number % i == 0) return false;
        }
        return true;
    }
}



import static org.junit.jupiter.api.Assertions.assertTrue;
import org.junit.jupiter.api.Test;

public class PrimeUtilTest {
    @Test
    public void testIsPrime() {
        PrimeUtil primeUtil = new PrimeUtil();
        assertTrue(primeUtil.isPrime(5));
    }
    
    @Test
    public void testIsNotPrime() {
        PrimeUtil primeUtil = new PrimeUtil();
        assertFalse(primeUtil.isPrime(4));
    }
}

tasks 30 

public class StringReplaceUtil {
    public String replaceCharacter(String str, char oldChar, char newChar) {
        return str.replace(oldChar, newChar);
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class StringReplaceUtilTest {
    @Test
    public void testReplaceCharacter() {
        StringReplaceUtil stringReplaceUtil = new StringReplaceUtil();
        assertEquals("helLo", stringReplaceUtil.replaceCharacter("hello", 'l', 'L'));
    }

    @Test
    public void testReplaceNonExistingCharacter() {
        StringReplaceUtil stringReplaceUtil = new StringReplaceUtil();
        assertEquals("hello", stringReplaceUtil.replaceCharacter("hello", 'x', 'y'));
    }
}
